# AWS Service

<aside>
π‘ μλΉμ€ λ³ μ€μ λ΄μ© μ λ¦¬, μλΉμ€ λΉκ΅

</aside>

[Amazon FSx](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20FSx%20845b8c86662e4062a53c6828b356dd10.md)

[AWS EMR](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20EMR%20397da58786254bf7b07a33cee4180f91.md)

[AWS Glue](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Glue%20e9f2f556a355472bb764b67679d8dee2.md)

[Amazon Inspector](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20Inspector%207bb1c216efb148179dee9e05a7717211.md)

[Trusted Advisor](AWS%20Service%20d9b871590f6248af933993c833db31e1/Trusted%20Advisor%20842a84fdb2f240f4806999abe4d41eac.md)

---

## Computing

[Amazon ECS](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20ECS%2053345fe5be6f4c2890b8ea1b987a6245.md)

[Lambda](AWS%20Service%20d9b871590f6248af933993c833db31e1/Lambda%20d05d9c10221941f88530ad9c8bc921d3.md)

[Elastic Beanstalk](AWS%20Service%20d9b871590f6248af933993c833db31e1/Elastic%20Beanstalk%20c41e864f0c56427cad45db01fc2560b8.md)

[EC2 Auto Scaling](AWS%20Service%20d9b871590f6248af933993c833db31e1/EC2%20Auto%20Scaling%20a8c73e54271047348bb104ebb8516099.md)

### Lambda vs. ECS Fargate

> **`Fargate`**: AWS μ»¨νμ΄λ κΈ°λ° μλ²λ¦¬μ€ μ»΄ν¨ν μλΉμ€λ‘, ECSμ EKSλ₯Ό κΈ°λ°μΌλ‘ λμ
λ³λμ EC2 μΈμ€ν΄μ€ μμ΄λ μ»¨νμ΄λλ₯Ό μ€νν  μ μκ² ν΄μ€
βμ»¨νμ΄λ κΈ°λ°β μ°¨μ΄ - μ€ν νκ²½μ λλ€λ³΄λ€ μμ λ‘­κ² κ΅¬μ± κ°λ₯
`labmda`μ λΉν΄ μ€ν μλκ° λλ¦¬κ³ , λμ μ€ν νμ€ν¬ μκ° μ κ³  λΉμΈλ€.
μ΅λ μ€ν μκ°μ μ νμ΄ μλ€. *(λλ€λ μ΅λ μ€ν μκ°μ΄ 15?λΆ, warm cold μνμ λ°λΌ μ°¨μ΄κ° μκΈ΄ νμ§λ§)*
> 

## Messaging

[SQS](AWS%20Service%20d9b871590f6248af933993c833db31e1/SQS%20de166bae37b34e9c95cb8ace3e8ccdcf.md)

[SNS](AWS%20Service%20d9b871590f6248af933993c833db31e1/SNS%20799bf1209cb3421a85f3707fade79cae.md)

[Amazon EventBridge](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20EventBridge%20085c20b71fae4a3baaff20e1a5ff23fa.md)

[Amazon Lightsail](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20Lightsail%20b16b6c6cb6604e2e9c1000f149306b13.md)

### SQS vs. SNS

> SNS: broadcasting λ°©μ, μ£Όμ (topic)μ λν κ΅¬λμλ€μκ² λ©μΈμ§λ₯Ό λͺ¨λ λΏλ¦Ό 
SQS: μλΉμ€(1κ°, λ³΄ν΅ EC2)κ° λκΈ°μ΄μμ λ©μΈμ§λ₯Ό polling ν΄μΌ ν¨
> 
> 
> [[AWS] SNS vs SQS μ°¨μ΄μ ](https://seohyun0120.tistory.com/entry/AWS-SNS-vs-SQS-%EC%B0%A8%EC%9D%B4%EC%A0%90)
> 

### SNSλ‘ μ΄λ©μΌ λ³΄λ΄κΈ°?

---

## Storage

[Amazon EBS](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20EBS%2038cdf07aae044483900b36899e404054.md)

[EFS](AWS%20Service%20d9b871590f6248af933993c833db31e1/EFS%207332e623fd6845428e9a0803231aa235.md)

[Amazon S3](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20S3%203abdfdacf0a94ca3afa296ea2711c969.md)

[AWS Storage Gateway](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Storage%20Gateway%205c804defc24c406da6fcf321ead329cf.md)

[DynamoDB](AWS%20Service%20d9b871590f6248af933993c833db31e1/DynamoDB%20b0095fdfc2e34bb7b64d1c8e22d1f09c.md)

[Redis](AWS%20Service%20d9b871590f6248af933993c833db31e1/Redis%20134e69c4bda241ecad92fa086c9461cf.md)

[Aurora](AWS%20Service%20d9b871590f6248af933993c833db31e1/Aurora%2088089f15007d4101bee1f2826928130e.md)

[EC2 Instance Store](AWS%20Service%20d9b871590f6248af933993c833db31e1/EC2%20Instance%20Store%20318e3c8e5092458184ce40c8334bce9c.md)

### EFS vs. Others

> λ€λ₯Έ μ€ν λ¦¬μ§λ EC2 νλμ ν κ°λ§ κ²°ν©νμ¬ μ¬μ©ν  μ μλ λ°λ©΄, EFSλ μ¬λ¬ EC2κ° λμμ μ κ·Όν  μ μμ **(ACID λ³΄μ₯)**
> 

### RDSμ νμ¬ λ°μ΄ν°μ μλ‘μ΄ λ°μ΄ν°λ₯Ό μνΈννκΈ°

- μ΄λ―Έ κ°λ μ€μΈ DBλ₯Ό μνΈν λͺ»ν¨
- μνΈν λμ§ μμ μνλ‘ read replica μμ±ν΄μ μνΈν λͺ»ν¨
- **μνΈνλ snaptshotμ μμ±νκ³  κ·Έκ±Έλ‘ RDS μΈμ€ν΄μ€ λ³΅κ΅¬**

### RDS Read Replica vs. Multi AZ

λ λ€ durability (λ΄κ΅¬μ±)

> `Multi-AZ`λ λ€λ₯Έ AZμ RDSλ₯Ό λκΈ°νμμΌμ primary RDS fail μΌ λ λ³΅μνκΈ° μν΄ standby, **λ³΅μλ ₯ νΉμ κ°μ©μ±,** **λκΈ° λ³΅μ 
μ΅μ 2κ°μ΄μμ AZ in single region**
> 

> `Read replica`λ μ½κΈ° μμ²­μ λμμ μ²λ¦¬νκ² ν΄μ νΈλν½ λΆμ°μ μ΄μ μ λ§μΆ€, **μ±λ₯, scaling,** **λΉλκΈ° λ³΅μ 
νλμ AZ, Cross-AZ, Cross-Region**
> 

![Untitled](AWS%20Service%20d9b871590f6248af933993c833db31e1/Untitled.png)

### S3μμ data duration κ³ λ €νκΈ°

> ν­μ s3-IAκ° standardλ³΄λ€ cost-effectiveν κ²μ μλλ€.
> 

> `S3-IA`λ μ΅μ 30μΌκ° λ°μ΄ν°λ₯Ό λ³΄κ΄ν΄μΌνκΈ° λλ¬Έμ μ§§μ κΈ°κ°λμ μ μ§λ  λ°μ΄ν°λ₯Ό μ μ₯ν  λλ κ·Έλ₯ standardκ° λ«λ€.
> 

ex. μ€κ° μΏΌλ¦¬λ₯Ό 24μκ°μ λ μ μ₯ν  λͺ©μ μΌλ‘λ S3 Standardκ° λΉμ© ν¨μ¨μ μΈ μ΅μμ΄λ€. = μ΄μ°¨νΌ 24μκ° μ μ₯ν΄λ λ€λ₯Έ μ΅μμ 30μΌμΉ (νΉμ 90μΌμΉ) μκΈ μ²­κ΅¬λ¨

## Networking & Content Transfer

[Load Balancer](AWS%20Service%20d9b871590f6248af933993c833db31e1/Load%20Balancer%20e7fd922de9cf4f309646759a98da3d4e.md)

[CloudFront](AWS%20Service%20d9b871590f6248af933993c833db31e1/CloudFront%2021d08bc723e4497a82f2c20c440f7511.md)

[API Gateway](AWS%20Service%20d9b871590f6248af933993c833db31e1/API%20Gateway%20fc5e1527ced147c2b201a5d6cd0cd93e.md)

[AWS Step Functions](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Step%20Functions%20d6c48700d95a4e17a2e51c159125858d.md)

[AWS Direct Connect](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Direct%20Connect%20c9bf7f62dd024a5ba89f94a9254fb7a2.md)

[Network Access Control List(ACL) vs. Security Group](AWS%20Service%20d9b871590f6248af933993c833db31e1/Network%20Access%20Control%20List(ACL)%20vs%20Security%20Group%20c33b59cee8d94458a22092f692436bb5.md)

[AWS Transit Gateway](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Transit%20Gateway%20f753ced669f94694a6618eec3db7ea4a.md)

[AWS Global Accelerator](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Global%20Accelerator%20f338435149ef4c89bbf49bd5d967d4eb.md)

[AWS WAF](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20WAF%20cdb13bd5913243bda030b6d4ef796b7f.md)

[DNS](AWS%20Service%20d9b871590f6248af933993c833db31e1/DNS%20664bf446f6be4e1b91aedf35a75949c7.md)

- Load Balancer vs. Routing
    
    ALBλ₯Ό μ΄μ©ν΄μ headerμ λ°λΌ μ΄λ€ μλ²λ‘ νΈλν½μ λ³΄λΌμ§ κ²°μ ν  μ μλλ°(?) μ΄ κ°λμ΄ λΌμ°νμ΄ μλκ°? β λ§λ€. LBλ νΈλν½μ λΌμ°ννλ€λ μ©μ΄ μ¬μ©.
    λ€λ§ route53κ³Ό LBλ μ§μ­/AZ μΈμ§ λ²μκ° λ€λ¦
    

### μ§λ¦¬μ  μ ν

β­ κ° μλΉμ€μ μ§λ¦¬μ  μ ν κΈ°λ₯μ΄ μ¬λ°λ₯Έ λ²μμμ μ€νλλμ§ νμΈν  κ² (ex. CloudFront georestriction in VPCβ)

1. georestriction through CloudFront
    
    > georestriction = geo-blocking (CFμ κΈ°λ₯)
    > 
    
    > νμ©λ κ΅­κ°μμλ§ μ½νμΈ μ μ κ·Όνλλ‘ or κΈμ§λ κ΅­κ°μμ μ κ·Όνμ§ λͺ»νλλ‘
    > 
2. Route53 - geolocation routing policy
    
    > μ λ½μμ λ°μνλ λͺ¨λ  μΏΌλ¦¬λ₯Ό νλν¬νΈλ₯΄νΈ λ¦¬μ μ μλ ELBλ‘ λΌμ°νΈλλλ‘ μ‘°μ ν  μ μλ€.
    > 
    
    > λ°°ν¬ κΆνμ΄ μλ μ§μ­μλ§ μ½νμΈ  λ°°ν¬νλλ‘ ν  μ μλ€.
    > 
3. WAF + ALB in VPC
    
    > WAFκ° geo match condition μ§μ (+ACL)
    > 

`security group`μ μ§λ¦¬ μ ν λͺ»ν¨

β`ACL`λ§μΌλ‘λ μ§λ¦¬ μ νμ λͺ»νλ λ―?

### π΄Privat Link vs. Direct Connect vs. VPC

---

## Logging and Monitoring

[Amazon CloudWatch](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20CloudWatch%20eb139430e3ce4019a1aaf7805f9c4142.md)

[CloudTrail](AWS%20Service%20d9b871590f6248af933993c833db31e1/CloudTrail%204e1fa123473b4637b1b6102f5cfb370e.md)

[Kinesis](AWS%20Service%20d9b871590f6248af933993c833db31e1/Kinesis%207db9303efa7c40538df82f9a2d683844.md)

### Management

[CloudFormation](AWS%20Service%20d9b871590f6248af933993c833db31e1/CloudFormation%20c7a7509b925f4a7288fecb4d4dfd52e3.md)

## Security & Compliance

[KMS (Key Management Service)](AWS%20Service%20d9b871590f6248af933993c833db31e1/KMS%20(Key%20Management%20Service)%20dd629b8df7fa406798278fd273cbe74e.md)

[IAM](AWS%20Service%20d9b871590f6248af933993c833db31e1/IAM%20b8fb0f7e602d4817b2c3fab4e5d3eda9.md)

[AWS Shield](AWS%20Service%20d9b871590f6248af933993c833db31e1/AWS%20Shield%20620bba93f09f4517912d158c93ff876c.md)

[GuardDuty](AWS%20Service%20d9b871590f6248af933993c833db31e1/GuardDuty%2092f910c188c243c0b4ebe763ca278c2b.md)

[Resource Access Manager](AWS%20Service%20d9b871590f6248af933993c833db31e1/Resource%20Access%20Manager%20e15cadc8a70f4f75844f07e3b264a060.md)

[OpsWorks](AWS%20Service%20d9b871590f6248af933993c833db31e1/OpsWorks%2035341c7c2d634587a04f69b07a83f8d2.md)

[Amazon Cognito](AWS%20Service%20d9b871590f6248af933993c833db31e1/Amazon%20Cognito%20c693f9db42c3471081c6c37c2229ad74.md)

### Organization vs. Single sign-on

> `**AWS Organization**`: μ¬λ¬ AWS κ³μ μ μ‘°μ§μΌλ‘ λ¬Άμ΄μ μ€μ κ΄λ¦¬
κ³μ  κ΄λ¦¬, ν΅ν© μ²­κ΅¬ κΈ°λ₯
**μ°ν© capability μ κ³΅ X**
> 

> `**AWS SSO**` : μ€μνλ λλ ν λ¦¬μ μλ κ·Έλ£Ή λ©€λ²μ λ°λΌ μ°ν© μ κ·Ό κΆν μ μ κ°λ₯
λ€μ€ λλ ν λ¦¬λ₯Ό μ¬μ©νκ³  user νΉμ±μ λ°λΌ κΆνμ κ΄λ¦¬νκ³  μΆλ€λ©΄ `IAM` μ¬μ©
>