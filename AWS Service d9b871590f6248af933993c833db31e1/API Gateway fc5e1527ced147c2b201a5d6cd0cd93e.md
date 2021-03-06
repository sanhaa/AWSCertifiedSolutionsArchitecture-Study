# API Gateway

<aside>
๐ก ๊ฐ๋ฐ์๊ฐ API๋ฅผ ์์ฑ, ์ ์ง, ๋ชจ๋ํฐ๋งํ๊ธฐ ์ฝ๊ฒ ๋ง๋ค์ด์ฃผ๋ ์์  ๊ด๋ฆฌํ ์๋น์ค

</aside>

1. RESTful API
    1. HTTP-based
    2. stateless client-server communication
    3. ํ์ค HTTP methods ๊ตฌํ (GET, POST, PUT, DELETE)
2. WebSocket API
    1. Websocket protocol ๊ธฐ๋ฐ
    2. stateful, full-duplex communication between client - server
    

[Study/HTTP.md at main ยท Sanhaa/Study](https://github.com/Sanhaa/Study/blob/main/Network/HTTP.md)

### โ์ RESTful API๊ฐ stateless ์ธ๊ฐ?

<aside>
๐ก RESTful API๋ REST์ ๊ธฐ๋ฐํ API์ด๊ณ , REST๋ **HTTP** ํ๋กํ ์ฝ์ ๊ธฐ๋ฐํ ์ํคํ์ฒ์ด๋ค. HTTP๋ stateless protocol ์ด๋ฏ๋ก RESTful API๋ ๋ง์ฐฌ๊ฐ์ง์ด๋ค.

</aside>

HTTP๋ ์ stateless์ธ๊ฐ?

**HTTP ํน์ง**

- HyperText Transfer Protocol
- HTTP๋ผ๋ ํ๋กํ ์ฝ์ www์ ๊ธฐ๋ณธ์ด ๋๋ ํต์  ๊ท์ฝ์ผ๋ก,
- ํด๋ผ์ด์ธํธ(์์ฒญ) - ์๋ฒ(์๋ต) ๊ตฌ์กฐ๋ก ์ค๊ณ๋์๋ค.
- ์์ฒญ - ์๋ต์์ stateless, connectionless ํน์ง์ ๊ฐ์ง๋ค.

**HTTP Stateless**

- ์๋ฒ์ ํด๋ผ์ด์ธํธ๊ฐ ์์ฒญ์ ๋ณด๋ผ ๋, ํ ๋ฒ์ ๋ชจ๋  ์ ๋ณด๋ฅผ ํฌํจํ๋๋ก ํด์ผ ํ๋ค.
- ์๋ฒ๋ ํด๋ผ์ด์ธํธ์ ์ด์  ์ํ(state)๋ฅผ ์ ์ฅํ์ง ์๊ธฐ(less) ๋๋ฌธ์ด๋ค.
- ex. Stateless) ์๋ฉ๋ฆฌ์นด๋ธ ์์ด์ค๋ก ์ฃผ์ธ์. ๊ฒฐ์ ๋ ์นด๋๋ก ํ ๊ฑฐ์์.
- ex. Stateful) ์๋ฉ๋ฆฌ์นด๋ธ ์ฃผ์ธ์. โ (์์ด์ค or ํซ?) โ ์์ด์ค๋ก ํ ๊ฒ์ โ (๊ฒฐ์  ์๋จ์?) โ ์นด๋์

**Stateless ํน์ง**

- ๊ฐ ์์ฒญ(request)๋ ๋ณ๊ฐ๋ก ์ฒ๋ฆฌ๋๋ค.
- = ์์ฒญ๋ค๋ผ๋ฆฌ ์ํฅ์ ๋ฐ์ง ์๋๋ค.
- ๊ฐ request๋ server๊ฐ ์ดํดํ  ์ ์๋๋ก ํ์ํ ์ ๋ณด๋ฅผ ๋ชจ๋ ํฌํจํด์ผ ํจ.
- storing session state on the server = REST ๊ตฌ์กฐ์ stateless ์ ์ฝ์ ์๋ฐํ๋ค. session state๋ ์ ์ ์ผ๋ก ํด๋ผ์ด์ธํธ ์ธก์์ ๊ด๋ฆฌ๋์ด์ผ ํ๋ค.