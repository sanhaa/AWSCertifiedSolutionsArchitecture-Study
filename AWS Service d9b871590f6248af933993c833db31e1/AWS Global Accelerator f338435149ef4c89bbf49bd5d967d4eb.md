# AWS Global Accelerator

<aside>
๐ก ๊ธ๋ก๋ฒํ๊ฒ ์ ๊ณต๋  ์ ํ๋ฆฌ์ผ์ด์์ ๊ฐ์ฉ์ฑ๊ณผ ์ฑ๋ฅ์ ๋์ด๊ธฐ ์ํ ๋คํธ์ํน ์๋น์ค

</aside>

> AWS ์์ฒด global network๋ฅผ ํ์ฉํด์ user โ application ์ธํฐ๋ท ํธ๋ํฝ์ ์ง์ ์ ์ผ๋ก ์ฐ๊ฒฐํจ
> 

### ํน์ง

- application endpoint๋ฅผ ์ง์์ ์ผ๋ก ๋ชจ๋ํฐ๋ง
- ๊ฐ์ฅ ๊ฐ๊น์ด `healthy endpoints`๋ก traffic์ ๋ผ์ฐํ ํจ
- `static IP address` ์ ๊ณต - fixed entry point to app
- โ ํน์  IP ์ฃผ์๋ฅผ ๊ฐ๊ธฐ ๋ค๋ฅธ AWS region๊ณผ AZ์์ ๊ด๋ฆฌํ๋ ๋ณต์ก๋๋ฅผ ์ ๊ฑฐ
- TCP or UDP proxying packetsํ์ฌ ์ฑ๋ฅ ๋์

### non-HTTP use case์ ์ ๋ง์

- `gaming`(UDP), `IoT` (MQTT), `Voice over IP`
- ๋ฌผ๋ก  HTTP use case์๋ ์ ๋ง์. ํนํ static IP ์ฃผ์๊ฐ ํ์ํ  ๋