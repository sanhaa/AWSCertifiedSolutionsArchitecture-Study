# IAM

<aside>
๐ก ์๋ณ๊ณผ ์ ๊ทผ ๊ด๋ฆฌ Identity and Access Management

</aside>

> ์๋น์ค, ๋ฆฌ์์ค ์ก์ธ์ค ๊ด๋ฆฌ, **target = user, groups, roles, AWS resources**
> 
- ์ด๋ user, group, role ๋ค์ `IAM indentities` ๋ผ๊ณ  ํจ

## ๊ธฐ๋ณธ ๋ด์ฉ

- `IAM identities`: users, groups of users, roles
- `IAM principal`: user or role
- `IAM entity`: user or role
- `Policy`: identity๋ resource์ ์ฐ๊ณ๋์ด permission์ ์ ์
- AWS๋ IAM principal (user or role)์ด ์์ฒญ์ ๋ณด๋ผ ๋ policies ๊ฒํ ํจ
- `Permission`: ์์ฒญ์ ํ์ฉ/๊ฑฐ๋ถ๋ฅผ ๊ฒฐ์ ํ๋ ๊ถํ, in policy
- Polilcy ์ ์ฅ = JSON document (๋จ, ACL ์ ์ธ)

### Policy type (6๊ฐ์ง)

1. **`Identity-based policy`:** IAM identities์ policy ๋ถ์ฌ
    
    > user, group, role
    > 
    1. Managed policies: standalone ์ ์ฑ
    2. Inline policies: ํ๋์ user, group, role์ ์ง์ ์ ์ผ๋ก ์ถ๊ฐํ๋ ์ ์ฑ (policy - identity ๊ฐ 1๋ 1๊ด๊ณ)
2. **`Resource-based policy`** : resource์ inline policies ๋ถ์ฌ
    
    > resource
    > 
    1. ex. S3 bucket ์ ์ฑ, IAM role trust policy
3. **`Permission boundary` :** IAM entity์๊ฒ permission boundary๋ฅผ ์ง์ ํ๋ policy ์ฌ์ฉ
    
    > user, group, role
    > 
    1. identity-based policies๊ฐ entity์๊ฒ ๋ถ์ฌํ  ์ ์๋ ์ต๋ permission์ ์ ์
    2. โpermission์ ๋ถ์ฌํ๋ ๊ฒ์ ์๋โ
    3. resource-based policy๊ฐ ๋ถ์ฌํ  ์ ์๋ ์ต๋ ๊ถํ์ ์ ์ํ์ง๋ ์์
    4. ex. user or role (entity)์ permission boundary๊ฐ ์ ์ฉ๋๋ฉด, ๊ทธ entity๋ indentity-based policies์ permission boundaries ๋ชจ๋ ๋ง์กฑํ๋ ํ๋๋ง ์ํํ  ์ ์์
4. **`Organization SCP`** : ์กฐ์ง์ ๊ณ์  ๋ฉค๋ฒ, ์กฐ์ง ์ ๋์ ์ต๋ permission์ ์ ์ํ๋ AWS Organization service control policy๋ฅผ ์ฌ์ฉ
    
    > AWS organizations organizational unit
    > 
    1. identity-based policies or resource-based policies๊ฐ ๋ถ์ฌํ  ๊ถํ์ ์ ํ
    2. (๋ง์ฐฌ๊ฐ์ง๋ก) ๊ถํ์ ์ง์  ๋ถ์ฌํ์ง๋ ์์
5. **`ACL(Access control list)`** : ๋ค๋ฅธ ๊ณ์ ์ ์ด๋ค principal์ด resource์ ์ ๊ทผํ  ์ ์๋์ง ์ปจํธ๋กค
    
    > resource
    > 
    1. resource-based policy์ ๋น์ท
    2. JSON policy document ๊ตฌ์กฐ๋ฅผ ์ฌ์ฉํ์ง๋ ์์
    3. ํน์  principal์ ๊ถํ์ ๋ถ์ฌํ๋ cross-accound permission policies
    4. ๊ฐ์ ๊ณ์ ์ ๋ค๋ฅธ entity์๊ฒ ๊ถํ ๋ถ์ฌ X
6. **`Session policy`** : AWS CLI or AWS API๋ฅผ ์ฌ์ฉํ  ๋, role๊ณผ federated user๋ฅผ ๊ฐ์ ํ๊ธฐ ์ํด ์ฌ์ฉ
    
    > role or federated user session
    > 
    1. session์ role์ด๋ user์ identity-based policies๋ฅผ ๋ถ์ฌํ๋ ๊ถํ์ ์ ํํจ
    2. ์์ฑ๋ ์ธ์์ ๊ถํ์ ์ ํํ  ๋ฟ, ๊ถํ์ ๋ถ์ฌํ์ง๋ ์๋๋ค.

### Identity-based vs. resource-based policies

![Untitled](IAM%20b8fb0f7e602d4817b2c3fab4e5d3eda9/Untitled.png)

**Identity-based**

```json
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "s3:ListBucket",
    "Resource": "arn:aws:s3:::example_bucket"
  }
}
```

**Resource-based**

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Sid": "1",
    "Effect": "Allow",
    "Principal": {"AWS": ["arn:aws:iam::account-id:root"]},
    "Action": "s3:*",
    "Resource": [
      "arn:aws:s3:::mybucket",
      "arn:aws:s3:::mybucket/*"
    ]
  }]
}
```

## IAM users

- AWS์ ์ํธ์์ฉํ  IAM user = ์ฌ๋ or service
- ์ฃผ๋ก ์ฌ์ฉ: ๋๊ตฐ๊ฐ์๊ฒ AWS ๊ด๋ฆฌ ์ฝ์์ ๋ก๊ทธ์ธํ  ๋ฅ๋ ฅ์ ์ฃผ๊ฑฐ๋, API or CLI๋ฅผ ์ฌ์ฉํ์ฌ AWS ์๋น์ค ํ๋ก๊ทธ๋จ์ ์ธ ์์ฒญ์ ๋ง๋ค ๋
- IAM user ์์ฑํ ํ, ๊ถํ ์ฃผ๋ ๋ฐฉ๋ฒ ๋ ๊ฐ์ง
    1. ํน์  ๊ถํ ์ ์ฑ์ด ์๋ user group์ ๋ฉค๋ฒ๋ก ์ค์ 
    2. user์๊ฒ ์ง์ ์ ์ผ๋ก ์ ์ฑ์ ๋ถ์ฌ

> โ IAM account์์ IAM user ์์ฑํ  ์ ์๋?
> 

### IAM user vs. IAM roles

AWS์์ ๋ญ๋ฅผ ํ  ์ ์๊ณ  ํ  ์ ์๋์ง๋ฅผ ๊ฒฐ์ ํ๋ ๊ถํ ์ ์ฑ

์ฐจ์ด์ : role์ credential ์๋ค. (๋น๋ฐ๋ฒํธ๋ ์ ๊ทผ ํค ๋ฑ) โ ํน์  ์ฌ๋๊ณผ ์ฐ๊ฒฐ๋ ๊ฒ ์๋๋ผ ํ์ํ ๋๊ตฐ๊ฐ๊ฐ ์ญํ ์ ๊ฐ์ง๊ฒ ๋จ.

IAM user๋ ํน์  task์ ๋ํด ์์์ ์ผ๋ก ๋ค๋ฅธ ๊ถํ์ ๊ฐ์ง๊ฒ ๋  ์ ์์ 

๋ชจ๋  ๊ฒฝ์ฐ์ IAM ๊ณ์ ์ ๋ง๋ค์ด์ ๊ถํ์ ๋ถ์ฌํ  ํ์ ์๋ค. ์ฅ๊ธฐ์ ์ผ๋ก credentialํ๋ ค๋ฉด IAM user๋ฅผ ๋ง๋ค๊ณ , ๊ทธ๋ ์ง ์๊ณ  ์์์ ์ผ๋ก ๊ถํ์ ๊ถํ์ ํ์ฉํ๋ ค๋ฉด IAM role์ ์ฌ์ฉ

- IAM user๋ฅผ ์์ฑํด์ผ ํ๋ ๊ฒฝ์ฐ
    - AWS ๊ณ์ ์ ์์ฑํ ํ, ๊ทธ ๊ณ์ ์์ ํผ์ ์์ํ๋ค๋ฉด
        
        > root user ๊ถํ์ผ๋ก AWS๋ฅผ ์ฌ์ฉํ  ์ ์์ง๋ง ์ถ์ฒํ์ง ์์
        ์์ ์ ๋ํ IAM user๋ฅผ ์์ฑํ๊ณ  ์ฌ์ฉํ๋ ๊ฒ์ ์ถ์ฒ
        > 
    - AWS ๊ณ์ ์์ ์ฌ๋ฟ์ด ์ผํด์ผ ํ๊ณ , user group์ด ๋ค๋ฅธ ์๋ณ ๋ฉ์ปค๋์ฆ์ด ์๋ค๋ฉด
        
        > AWS ๋ฆฌ์์ค์ ์ ๊ทผํ  ๊ฐ์ธ์ ์ํ IAM user๋ฅผ ์์ฑํ๊ณ  ๊ฐ์์๊ฒ credential ์ฃผ๊ธฐ.
        ์ฌ๋ฌ๋ช์ด credential ๊ณต์ ํ์ง ์๋ ๊ฒ์ ์ถ์ฒ
        > 
- IAM role์ ์์ฑํด์ผ ํ๋ ๊ฒฝ์ฐ
    - EC2์์ ๋์ํ๋ ์ดํ๋ฆฌ์ผ์ด์์ ์ ์ ์ค์ธ๋ฐ, ๊ทธ ์ฑ์ด AWS์ ์์ฒญ์ ๋ณด๋ผ ๋
        
        > application์ IAM user๋ฅผ ์์ฑํ๊ณ  credentials์ ๋๊ธฐ๊ฑฐ๋ application์ credential์ ์๋ฒ ๋ ํ์ง ๋ง์๋ผ.
        EC2 ์ธ์คํด์ค์ attachํ  IAM role์ ์์ฑํ๊ณ  ๊ทธ ์ธ์คํด์ค์์ ๋์ํ๋ ์ ํ๋ฆฌ์ผ์ด์์ ์์ security credential ์ฃผ๊ธฐ
        > 
    - mobile phone์์ ๋์ํ๋ ์ดํ๋ฆฌ์ผ์ด์, AWS์ ์์ฒญ์ ๋ณด๋ผ ๋
        
        > IAM user๋ฅผ ์์ฑํ๊ณ  app์ IAM user์ access key๋ฅผ ๋ถ์ฐํ์ง ์๋๋ก
        ์ธ์ฆ๋ user๋ก ๋ก๊ทธ์ธํ๋๋ก ํ๊ณ , user์ IAM role๋ฅผ ์ฐ๊ฒฐ์ํค๊ธฐ
        ์ฑ์ ๊ทธ role์ ์ฐ๊ฒฐ๋ ์ ์ฑ์ด ๋ช์ํ ๊ถํ์ ๊ฐ์ง ์์ security credentials์ ์ป์ ์ ์์.
        > 
    - ํ์ฌ ์ฌ๋์ด ํ์ฌ ๋คํธ์ํฌ์ ์์ ๋ ์ธ์ฆ๋๋ค. ๋ค์ ๋ก๊ทธ์ธํ์ง ์๊ณ ๋ AWS๋ฅผ ์ฌ์ฉํ๋๋ก ํ๊ณ  ์ถ์.
        
        > 
        > 
    

## MFA

<aside>
๐ก Multi Factor Authentication

</aside>

- IAM user or AWS account root user์ ๋ํด MFA  ํ์ฑํํ  ์ ์๋ค.

> ๋ณด์๊ฐํ๋ฅผ ์ํด ๋ก๊ทธ์ธ + ๋ณด์์ง๋ฌธ
> 
1. Virtual MFA device
2. U2F security key
3. HArware MFA device

[https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html)

[https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#managedpolicy](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#managedpolicy)