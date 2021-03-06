# Amazon S3

<aside>
๐ก ๊ฐ์ฒด ์คํ ๋ฆฌ์ง

</aside>

โ S3๋ data (from internet)์ ๊ฒฝ์ฐ ์ ์ก ์๊ธ์ด ์๋ค. (๋ณด๊ด ๊ธฐ๊ฐ๊ณผ storage class์ ๋ฐ๋ฅธ ์๊ธ๋ง)

โ object๊ฐ versioning ๋๋ฉด ๋ฒ์ ์ ๋ฐ๋ผ retain ๊ธฐ๊ฐ์ ๋ฌ๋ฆฌ ์ค์ ํ  ์ ์๋ค. 

## S3 Storage Class

1. **S3 Standard**
    
    ๋ฒ์ฉ
    
2. **S3 Intelligent-Tiering**
    
    ์ ์ ์๊ฑฐ๋ ๋ณํํ๋ ์ก์ธ์ค (์ก์ธ์ค ํจํด์ ๋ชจ๋ํฐ๋งํ์ฌ ๊ฐ์ฒด๋ฅผ ์ ๋ ดํ ์ก์ธ์ค ๊ณ์ธต์ผ๋ก ์๋ ๋ณํ)
    
3. **S3 Standard-IA**
    
    ๋น๋ฒํ์ง ์์ ์ก์ธ์ค, ๊ทธ๋ฌ๋ ๋น ๋ฅด๊ฒ ์ก์ธ์ค ํด์ผํ  ๋
    
4. **S3 One Zone-IA**
    
    ์ต์ 3๊ฐ์ AZ์ ๋ฐ์ดํฐ๋ฅผ ์ ์ฅํ๋ ๋ค๋ฅธ S3 ์คํ ๋ฆฌ์ง ํด๋์ค์ ๋ฌ๋ฆฌ ๋จ์ผ AZ์ ์ ์ฅ, ์ ๋ ด, ๊ฐ์ฉ์ฑ ๋ฎ์, ๋ณต์๋ ฅ ๋ฎ์ = 
    
5. **S3 Glacier Instant Retrieval**
    
    ๊ฑฐ์ ์ก์ธ์คํ์ง ์์, ๋ฐ๋ฆฌ์ด ๋จ์์ ๊ฒ์์ด ํ์ํ ์ฅ๊ธฐ ๋ฐ์ดํฐ, ๊ฐ์ฅ ์ ๋ ดํ ์์นด์ด๋ธ ์คํ ๋ฆฌ์ง
    
6. **S3 Glacier Flexible Refrieval**
    
    5 GIR๋ณด๋ค ๋ ์ ์ ์ก์ธ์ค, ๋น๋๊ธฐ์ ๊ฒ์(๋ช ๋ถ ~ ๋ช ์๊ฐ์ ์ก์ธ์ค ์๊ฐ), ๋ ์ ๋ ด
    
7. **S3 Glacier Deep Archive**
    
    ์์นด์ด๋ธ ์คํ ๋ฆฌ์ง ์ค์์๋ ๊ฐ์ฅ ์ ๋ ด, ์ฐ 1~2ํ, ๋ฐ์ดํฐ์ ์ฅ๊ธฐ ๋ณด๊ด
    
8. **S3 Outposts**
    
    ์จํ๋ ๋ฏธ์ค Outpost ํ๊ฒฝ์ ๊ฐ์ฒด ์คํ ๋ฆฌ์ง ์ ๊ณต
    

![Untitled](Amazon%20S3%203abdfdacf0a94ca3afa296ea2711c969/Untitled.png)

---

**Minimum storage duration charge**

> ์ต์ ๋ณด๊ด ๊ธฐ๊ฐ, ์ด๊ฒ๋ณด๋ค ๋ ์งง๊ฒ ๋ณด๊ดํด๋ ์ด ๊ธฐ๊ฐ๋งํผ ๋น์ฉ ์ฒญ๊ตฌ
> 

## ์ถ๊ฐ ๊ธฐ๋ฅ

### S3 Transfer Acceleration (S3TA)

<aside>
๐ก speed up content transfers to and from S3 (50~500%) ํฐ ์ค๋ธ์ ํธ, ์ฅ๊ฑฐ๋ฆฌ์ฉ

</aside>

- accelerated transfer์ ๋ํ ์๊ธ๋ง ์ง๋ถํ๋ฉด ๋๋ค.
- accelerate ํจ๊ณผ๋ฅผ ๋ชป๋ดฃ์ ๋๋ ์ง๋ถํ์ง ์์๋ ๋จ

### Multi part upload

<aside>
๐ก Object๋ฅผ ์ฌ๋ฌ ํํธ๋ก ๋ถํ ํ์ฌ ์๋ก๋

</aside>

`performance` `resilience`

### Versioning

<aside>
๐ก keep multiple variants of an object in same bucket

</aside>

- ํ ๋ฒ enable๋ก ์ค์ ํ๋ฉด unversioned state๋ก ๋๋๋ฆด ์ ์์

### S3์ scalability

- ์๋์ ์ผ๋ก ๋์ ์์ฒญ ์๋๋ฅผ ๋ฌ์ฑํ๊ธฐ ์ํด scaling

```
s3://{bucket_name}/{prefix}/{file_name}
```

- prefix ์ด์ฉ?? โ parallel reading ๊ฐ๋ฅ = performance ๋์ผ ์ ์๋ค.

### Lifecycle transition

**๋ถ๊ฐ๋ฅํ ์ ํ**

S3 Intelligent-Tiering โ S3 standard, S3 standard-IA

S3 One Zone-IA โ S3 standard-IA, S3-Intelligent-Tiering

- ํญ์ S3 standard๊ฐ ์๋จ์์ ์ ํ๋์ด์ผ ํ๊ณ , ์ ํ๋ ๊ฒฐ๊ณผ๊ฐ standard ์ผ ์๋ ์๋ค.
- ๋ง์ฐฌ๊ฐ์ง๋ก `ํญํฌ์` ํํ์ transition์ ์ด๋ฃจ๊ธฐ ๋๋ฌธ์ ํ๋จ โ ์๋จ ์ ํ์ ๋ถ๊ฐ๋ฅ

![Untitled](Amazon%20S3%203abdfdacf0a94ca3afa296ea2711c969/Untitled%201.png)

**์ ์ฝ**

> S3 standard โ S3 Standard-IA
> 

> S3 standard-IA โ S3 One zone-IA
> 
- **์ ํํ๊ธฐ ์ํด์๋ ์ต์ ๊ธฐ๊ฐ 30์ผ ํ์**