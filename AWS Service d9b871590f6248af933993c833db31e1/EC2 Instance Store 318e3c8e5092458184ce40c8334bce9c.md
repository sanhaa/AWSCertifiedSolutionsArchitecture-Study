# EC2 Instance Store

<aside>
๐ก temporary block-level storage for instance

</aside>

### ๋๋์ฒด Instance Store ์ ์ฐ๋

> ์ฅ๊ธฐ ๋ฐ์ดํฐ๋ X, ๋จ, ๋ฌผ๋ฆฌ์ ์ผ๋ก ๊ฐ์ ๋์คํฌ ๋ณผ๋ฅจ์ ์ฌ์ฉํ๊ธฐ ๋๋ฌธ์ IO ์ฑ๋ฅ์ ์์ฒญ ์ข์ `performance`
> 
1. ๋ฌด์กฐ๊ฑด `high performance` ํ์ํ๋ฐ, ์ฅ๊ธฐ ๋ณด๊ดํ๊ฑฐ๋ ๋ฐ์ดํฐ๋ฅผ ์ ์งํ  ํ์ ์์ ๋
2. or ๋ด๊ฒฐํจ์ฑ ์ํคํ์ฒ๊ฐ ๋ณด์ฅ๋์ด ์์ผ๋ฉด data loss ์ ๊ฒฝ์ฐ์ง ์๊ณ  high performance ์ด๋์ ์ทจํ  ์ ์์ 

### ํน์ง

- host computer์ ๋ฌผ๋ฆฌ์ ์ผ๋ก attached
- `์์ฃผ ๋ฐ๋๋` information์ `์์`๋ก ์ ์ฅํ๊ธฐ์ ์ด์์ 
- ex. buffers, caches, scratch data, `data that is replicated across a fleet of instances`
- instance type์ ๋ฐ๋ผ ์ง์ํ๋ instance store volume ๊ฐ์๊ฐ ๋ค๋ฆ

![Instance store ์์ ephemeral[0-23]๋ค์ store volumes](EC2%20Instance%20Store%20318e3c8e5092458184ce40c8334bce9c/Untitled.png)

Instance store ์์ ephemeral[0-23]๋ค์ store volumes

โ ์ ์ด์ instance = ๊ฐ์์ ์ปดํจํฐ 1๋์ธ๋ฐ, ์ฌ์ง์์ host computer๋ ๊ฐ๋ฐ์๊ฐ ์ค์ ํ  ์ ์๋ ๊ฑด์ง? 

> The virtual devices for instance store volumes areย `ephemeral[0-23]`. Instance types that support one instance store volume haveย `ephemeral0`. Instance types that support two instance store volumes haveย `ephemeral0`ย andย `ephemeral1`, and so on. 
โ โ ๊ทธ๋ผ ๊ณ์ ๋ณผ๋ฅจ์ด 1๊ฐ์ธ ์ธ์คํด์ค๋ง ์์ฑํ๋ฉด ephemeral0 ๋ณผ๋ฅจ๋ง ์ฌ์ฉํ๋ ๊ฑด์ง.
๊ทธ๋ฆฌ๊ณ  ๊ทธ๋ผ instances A์ B๊ฐ ๊ฐ์ ๋ณผ๋ฅจ์ ์ ๊ทผํ๊ฒ ๋๋ ๊ฑด์ง..
> 

### Instance Store lifetime

> The data in an instance store persists only during the lifetime of its associated instance
> 
- instance store volumes๋ ์ธ์คํด์ค ์์์์๋ง ๋ช์ํ  ์ ์๋ค. = ๋ณผ๋ฅจ์ ๋ผ์ด์ ๋ค๋ฅธ ์ธ์คํด์ค์ ๋ถ์ด๊ธฐ ๋ถ๊ฐ๋ฅ, **์ค๊ฐ์ ์ถ๊ฐ๋ ๋ถ๊ฐ๋ฅ**
- instance `๋ฆฌ๋ถํ`- instance store ์ ์ง
- **instance store ๋ฐ์ดํฐ ์ ์ค ๊ฒฝ์ฐ**
    - underlying `disk drive fails`
    - instance `stops`
    - instance `hibernates` (์ต๋ ์ ์ ๋ชจ๋)
    - instance `terminates`
- ์ธ์คํด์ค์ AMI๋ฅผ ์์ฑํ  ๊ฒฝ์ฐ: volume์ ์๋ ๋ฐ์ดํฐ ๋ณด์กดX, AMI๋ก ์คํํ ์ธ์คํด์ค์ ๋ณผ๋ฅจ์๋ ํ์๋์ง ์์