# ๐ Learned #27

# ๐ถ๋ธ๋ผ์ฐ์  ์ ์ฅ์

## Cookie & MaxAge & Expires

> **`์ฟ ํค(Cookie)`** ๋?
> ์น ๋ธ๋ผ์ฐ์  ์์ ์์ โํ์คํธ ํ์ผโ๋ก ์ ์ฅ์ด ๋๋ ๋ง๋ฃ ๊ธฐ๊ฐ์ด ์กด์ฌํ๋ ์ ์ฅ์๋ฅผ ์๋ฏธํฉ๋๋ค.

**`Expires`** : ์ฟ ํค๊ฐ ์ญ์ ๋๋ ๋ง๋ฃ ๋ ์ง๋ฅผ ์ค์ ํฉ๋๋ค.

```
๐ก ์ฟ ํค๋ฅผ ํ๊ธฐํ๋ ์์ฑ์๋๋ค. ํด๋น ๋ง๋ฃ์ผ์ UTC ์๊ฐ์ ๊ธฐ์ค์ผ๋ก ์ง์ ํฉ๋๋ค.
๐ก ๊ตฌ์กฐ: Expires=<date>

const expired = new Date();
expired.setTime(expired.getTime() + expiresHour * 24 * 60 * 60 * 1000);

// ์ฟ ํค ์์
document.cookie = `userId=adjh54; Path=/; Expires=${expired}`;
```

**`Max-Age`** : ์ฟ ํค๊ฐ ์ญ์ ๋  ์๊ฐ์ ์ด ๋จ์๋ก ์ค์ ํฉ๋๋ค
์ฟ ํค๋ฅผ ๋ฐ๋ก ์ค์ ํ์ง ์์๋ค๋ฉด ๋ธ๋ผ์ฐ์ ์ ์์กด์ฃผ๊ธฐ์ ๋์ผํ๊ฒ ๊ฐ๊ธฐ ๋๋ฌธ์ ์ฌ๋ผ์ง๊ฒ ๋ฉ๋๋ค. Max-Age ๋ผ๋ ์ต์์ ํตํด ๋ธ๋ผ์ฐ์ ์๋ ๋ณ๊ฐ๋ก ์ฟ ํค๋ฅผ ์ธ๋ถํ์ผ๋ก ์ ์ฅํ๋ ๊ฒ์ด ๊ฐ๋ฅํฉ๋๋ค.

```
๐ก expries์ ๋์์ผ๋ก ์ฟ ํค์ ๋ง๋ฃ์๊ฐ์ ์ค์ ํ  ์ ์๊ฒ ํด์ฃผ๋ ์์ฑ
๐ก ๊ตฌ์กฐ: Max-Age=<number>

// ์ฟ ํค ์์
document.cookie = `userId=adjh54; Path=/; Max-Age=3600`;
```

> expires(์ ํจ ์ผ์)๋ max-age(๋ง๋ฃ ๊ธฐ๊ฐ) ์ต์์ด **์ง์ ๋์ด์์ง ์์ผ๋ฉด**, _**๋ธ๋ผ์ฐ์ ๊ฐ ๋ซํ ๋ ์ฟ ํค๋ ํจ๊ป ์ญ์ ๋ฉ๋๋ค.**_ ์ด๋ฐ ์ฟ ํค๋ฅผ "์ธ์ ์ฟ ํค(session cookie)"๋ผ๊ณ  ๋ถ๋ฆ๋๋ค.

---

๐ ์ฐธ๊ณ ์๋ฃ
<br>
[![MaxAge/Expires_1](https://img.shields.io/badge/MaxAge/Expires_1-E8E8E8.svg?style=for-the-badge&logo=MaxAge/Expires_1&logoColor=white)](https://nyagm.tistory.com/177)
<br>
[![MaxAge/Expires_2](https://img.shields.io/badge/MaxAge/Expires_2-E8E8E8.svg?style=for-the-badge&logo=MaxAge/Expires_2&logoColor=white)](https://studee.tistory.com/55)
