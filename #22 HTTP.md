# ๐ Learned #22

# ๐ถHTTP

## 1. HTTP?

`HTTP`๋ ์ธํฐ๋ท์์ ๋ฐ์ดํฐ๋ฅผ ์ฃผ๊ณ ๋ฐ์ ์ ์๋ ํ๋กํ ์ฝ

## 2. HTTP ๋ฉ์ธ์ง ๊ตฌ์กฐ

HTTP ๋ฉ์์ง ํ์์ ๋ ๊ฐ์ง๊ฐ ์์ต๋๋ค.
`์์ฒญ(request)`์ ํด๋ผ์ด์ธํธ๊ฐ ์๋ฒ๋ก ์ ๋ฌํด์ ์๋ฒ์ ์ก์์ด ์ผ์ด๋๊ฒ๋ ํ๋ ๋ฉ์์ง๊ณ  ๊ณต๋ฐฑ์ ์ ์ธํ๊ณ  start line, headers, body๋ก 3๊ฐ์ง ๋ถ๋ถ์ผ๋ก ๋๋์ด์ง๋๋ค.
`์๋ต(response)`์ ์์ฒญ์ ๋ํ ์๋ฒ์ ๋ต๋ณ์ด๊ณ  ๊ณต๋ฐฑ์ ์ ์ธํ๊ณ  status line, headers, body๋ก 3๊ฐ์ง ๋ถ๋ถ์ผ๋ก ๋๋์ด์ง๋๋ค.

## 3. HTTP & HTTPS ์ฐจ์ด์ 

`HTTPS(https://)`๋ **SSL(Secure Socket Layer) ์ธ์ฆ์๋ฅผ ์ฌ์ฉํ๋ HTTP(http://)** ์๋๋ค. **SSL(๋๋ TLS) ์ธ์ฆ์๋ ์ผ๋ฐ HTTP ์์ฒญ ๋ฐ ์๋ต์ ์ํธํํฉ๋๋ค.**
๋ฐ๋ผ์ **HTTPS๋ HTTP๋ณด๋ค ๋ ์์ ํ ๋ณด์์ฉ ํ๋กํ ์ฝ์ด๋ผ๊ณ  ํ  ์ ์์ต๋๋ค**.

HTTP์ HTTPS์ ์ ์ผํ `์ฐจ์ด์ `์ **HTTPS๋ฅผ ์ฌ์ฉํ ์น ํ์ด์ง๋ฅผ ํตํด ์ ์ก๋๋ ๋ชจ๋  ๋ฐ์ดํฐ๋ ์ถ๊ฐ์ ์ธ ๋ณด์ ๊ณ์ธต**์ด ์์ต๋๋ค. ์ด๋ฅผ **TLS(์ ์ก ๊ณ์ธต ๋ณด์) ํ๋กํ ์ฝ**์ด๋ผ๊ณ  ํฉ๋๋ค. **๋ชจ๋  ์ ํ์ ๋ฐ์ดํฐ๋ ๋ณ๊ฒฝ๋๊ฑฐ๋ ์์๋  ์ ์๋ HTTPS ์ฌ์ดํธ๋ฅผ ํตํด ์ ๋ฌ๋๋ฉฐ ์ 3์๋ก๋ถํฐ ๋ณดํธ๋ฉ๋๋ค.**

---

๐ ์ฐธ๊ณ ์๋ฃ
<br>
[![HTTP_๋ฉ์ธ์ง_๊ตฌ์กฐ](https://img.shields.io/badge/HTTP_๋ฉ์ธ์ง_๊ตฌ์กฐ-E8E8E8.svg?style=for-the-badge&logo=HTTP_๋ฉ์ธ์ง_๊ตฌ์กฐ&logoColor=white)](https://hahahoho5915.tistory.com/62)
