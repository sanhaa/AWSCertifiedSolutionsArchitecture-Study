# Load Balancer

<aside>
๐ก Traffic ๋ถ์ฐ โ ์ฌ๋ฌ EC2 instances, containers, IP address, Lambda

</aside>

= Routing Traffic

`Route53`๊ณผ ์ฐจ์ด์ ์ route53์ ์ฌ๋ฌ region ๊ฐ์ ๋ผ์ฐํ์ ๋ด๋นํ์ง๋ง, LB๋ ๊ฐ์ ์ง์ญ์์ ๋ค๋ฅธ AZ ํน์ ๋ค๋ฅธ ์ธ์คํด์ค๋ค์๊ฒ ํธ๋ํฝ routingํฉ๋๋ค.

### Load Balancer์ ์ดํด (์ฑ๋ฅ x, `๋ณต์๋ ฅ` `๊ฐ์ฉ์ฑ`)

> ํธ๋ํฝ ๋ถ์ฐ์ด ๋ชฉ์ ์ด๋ค. ์ผ๋จ ๊ฐ์ ํธ๋ํฝ์ ์ฒ๋ฆฌํ๋ ์๋ฒ(instance, IP, container)๋ฅผ ๊ฐ์ฉ์ฑ์ ์ด์ ๋ก ์ฌ๋ฌ๋ ๋ ์ ์๋ค. ์ด๋ ๋ก๋ ๋ฐธ๋ฐ์๋ฅผ ์ด์ฉํด์ ์ฌ๋ฌ ์๋ฒ์ ํธ๋ํฝ์ ๋ณด๋ด์ผ ํ๋ค.
> 

> ๊ฒฐ๊ตญ, ๋ง์ ํธ๋ํฝ์ ์ฒ๋ฆฌํ๋ค๋ ๋๋๋ณด๋ค๋, `๊ฐ์ฉ์ฑ`์ ๋์ด๊ธฐ ์ํด ์ฌ๋ฌ ๋์ ์๋ฒ๋ฅผ ์ฌ์ฉํ๋ ค๋ฉด ๊ฑฐ์ณ์ผ ํ๋ layer
> 

> `๋ณต์๋ ฅ`์๋ ์ค๊ณ์ ๋ก๋ ๋ฐธ๋ฐ์๋ฅผ ์ฌ์ฉํ๋ ์ด์ ๋, ์ด๋ค ์ธ์คํด์ค๊ฐ fail์ผ ๋ ํธ๋ํฝ์ ๋ค๋ฅธ ์๋ฒ๋ก ๋ณด๋ด์ค ์ ์๊ธฐ ๋๋ฌธ์ด๋ค.
> 

## โญ Application Load Balancer

<aside>
๐ก 7๊ณ์ธต ๋ก๋ ๋ฐธ๋ฐ์

</aside>

> ์น ๊ฐ๋ฐํ  ๋, API ์์ฒญ์ ๋ฐ๋ผ ๊ฐ๊ธฐ ๋ค๋ฅธ MSA๋ฅผ ํธ์ถ
> 

target = instance, IP(private IP address ), container, lambda

### ALB type

1. Host-based Routing
    
    > HTTP header์ `Host` field (request hedaer ์์ฑ ์ค ํ๋)์ ๋ฐ๋ผ 
    ๊ฐ์ ๋ก๋ ๋ฐธ๋ฐ์๋ก๋ถํฐ `๋ค์ค ๋๋ฉ์ธ`์ผ๋ก routing
    > 
2. Path-based Routing
    
    > HTTP header์ `URL path`์ ๋ฐ๋ผ routing
    > 
3. HTTP header-based Routing
    
    > standard or custom HTTP header์ ๋ฐ๋ผ routing
    > 
4. HTTP method-based Routing
    
    > standard or custom HTTP method์ ์ํด routing
    > 
5. Query string parameter-based routing
6. Source IP address CIDR-based routing

### Content based routing

weighted load balancing

### ALB ์ค๋ฅ ์์

1. HTTP 502: Bad gateway
    
    > ๋ก๋ ๋ฐธ๋ฐ์๊ฐ ์์์น ๋ชปํ ์๋ต์ ๋ฐ์์ ๋, 
    TCP connection
    target response 
    SSL handshake error
    ๋ฑ๋ก๋์ง ์์ delay period
    Target is lambda function + response ๋ฌธ์ , ์๋ฌ
    > 
2. HTTP 504: Gateway timeout
    
    > ๋ชจ๋  timeout, ์ฐ๊ฒฐ ์๊ฐ์ด ์ง์  ์๊ฐ๋ณด๋ค ์ค๋ ๊ฑธ๋ฆฌ๋ฉด
    > 
3. HTTP 503: Service unavailable
    
    > load balancer์ ํ๊ฒ ๊ทธ๋ฃน์ด ๋ฑ๋ก๋์ง ์์์ ๋
    > 
4. HTTP 500: Internal Server error
    
    > WAF ACL์ ๊ตฌ์ฑํ๋๋ฐ ACL ๊ท์น์ ์๋ฌ๊ฐ ์์ ๋,
    ๋ก๋ ๋ฐธ๋ฐ์๊ฐ IdP ํ ํฐ๊ณผ ํต์ ํ  ์ ์๋ค. = ๋ณด์๊ทธ๋ฃน or ACL ๋ฌธ์ 
    > 
    

## Gateway Load Balancer