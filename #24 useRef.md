# ๐ Learned #24

# ๐ถ useRef

> `useRef`๋ ์ ์ฅ๊ณต๊ฐ ๋๋ DOM์์์ ์ ๊ทผํ๊ธฐ ์ํด ์ฌ์ฉ๋๋ React Hook์๋๋ค.
> ์ฌ๊ธฐ์ Ref๋ reference, ์ฆ **์ฐธ์กฐ**๋ฅผ ๋ปํฉ๋๋ค.

์ฐ๋ฆฌ๊ฐ ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ์ฌ์ฉ ํ  ๋์๋, ์ฐ๋ฆฌ๊ฐ ํน์  DOM ์ ์ ํํ๊ธฐ ์ํด์ querySelector ๋ฑ์ ํจ์๋ฅผ ์ฌ์ฉํฉ๋๋ค.

React๋ฅผ ์ฌ์ฉํ๋ ํ๋ก์ ํธ์์๋ ๊ฐ๋์ฉ DOM ์ ์ง์  ์ ํํด์ผ ํ๋ ์ํฉ์ด ํ์ํฉ๋๋ค. ๊ทธ๋ด๋ ์ฐ๋ฆฌ๋ useRef๋ผ๋ React Hook์ ์ฌ์ฉํฉ๋๋ค.

useRef๋ก ๊ด๋ฆฌ๋๋ ๊ฐ์ ๊ฐ์ด ๋ณํ๋์ด๋ ๋ฆฌ๋ ๋๋ง ๋์ง ์์ต๋๋ค.

## useRef๊ฐ ํ์ํ ์ํฉ

### 1. ์ปดํฌ๋ํธ์ focus๋ฅผ ์์น์ํฌ ํ์๊ฐ ์๋ ๊ฒฝ์ฐ.

-์๋ฅผ ๋ค์ด, ๊ฐ์ ์ฌ๋ฌ๊ฐ ์๋ ฅํ๊ณ  ์ฒซ ๋ฒ์งธ ์นธ์ผ๋ก ์ด๋ํด์ผ ํ๋ ๊ฒฝ์ฐ ํ์ํ๋ค.

```
//InputTest.js

import React, { useState, useRef } from 'react';

function InputTest() {
  const [text, setText] = useState('');
  const nameInput = useRef();

  const onChange = e => {
    setText(e.target.value)
  };

  const onReset = () => {
    setText('');
    nameInput.current.focus();
  };

  return (
    <div>
      <input
        name="name"
        onChange={onChange}
        value={text}
        ref={nameInput}
      />

      <button onClick={onReset}>์ด๊ธฐํ</button>
      <div>
        <b>๋ด์ฉ: </b>
        {text}
      </div>
    </div>
  );
}

export default InputTest;
```

const nameInput = useRef();
**ใด Ref ๊ฐ์ฒด๋ฅผ ๋ง๋ค์ด์ฃผ๊ณ **

<input
  name="name"
  onChange={onChange}
  value={text}
  ref={nameInput}
/>
**ใด ์ ํํ๊ณ  ์ถ์ DOM์ ์์ฑ์ผ๋ก ref ๊ฐ์ ์ค์ ํด์ค๋ค.**

nameInput.current.focus();
**: Ref ๊ฐ์ฒด์ current ๊ฐ์ ์ฐ๋ฆฌ๊ฐ ์ ํํ๊ณ ์ ํ๋ DOM์ ๊ฐ๋ฆฌํจ๋ค.
๊ทธ๋ฆฌ๊ณ  ํฌ์ปค์ฑ์ ํด์ฃผ๋ DOM API focus() ๋ฅผ ํธ์ถํ๋ค.**

### 2. ์์ฑ ๊ฐ์ ์ด๊ธฐํ(clear)ํ  ํ์๊ฐ ์๋ ๊ฒฝ์ฐ.

-์๋ฅผ ๋ค์ด, ์นด์ดํฐ์ ๊ฐ์ 0์ผ๋ก ์ด๊ธฐํ ํ  ํ์๊ฐ ์์ ๋. (ex.ํ์ด๋จธ 0์ผ๋ก ๋ง๋ค๊ธฐ)
-setInterval ์ด๋ setTimeout๊ณผ ๊ฐ์ ํจ์๋ clear ์์ผ์ฃผ์ง ์์ผ๋ฉด ๋ฉ๋ชจ๋ฆฌ๋ฅผ ๋ง์ด ์๋ชจํ๊ธฐ ๋๋ฌธ์ด๋ค.

```
// App.js

const RSPfunction = () => {
  const [result, setResult] = useState('');
  const [imgCoord, setImgCoord] = useState(rspCoords.๋ฐ์);
  const [score, setScore] = useState(0);
  const interval = useRef();

  useEffect(() => {
    interval.current = setInterval(changeHand, 100);
    return () => {
      clearInterval(interval.current);
    }
  }, [imgCoord]);
//  ์ฝ๋ ์๋ต
```

### 3. useRef๋ก ์ปดํฌ๋ํธ ์์ ๋ณ์ ๊ด๋ฆฌํ๊ธฐ

-๋ฆฌ ๋ ๋๋ง์ ํ์ง ์์ผ๋ฉด์ ์ปดํฌ๋ํธ์ ์์ฑ ์ ๋ณด๋ฅผ ์กฐํ & ์์ ํ  ๋

- useRef๋ฅผ ํ์ฉํ ๋ณ์๋ ์๋์ ๊ฐ์ ๊ณณ์ ์ฐ์ธ๋ค.
  -setTimeout, setInterval์ ํตํด ๋ง๋ค์ด์ง id
  -scroll ์์น -๋ฐฐ์ด์ ์ ํญ๋ชฉ์ ์ถ๊ฐํ  ๋ ํ์ํ ๊ณ ์ ๊ฐ key

```
// App.js

import React, { useRef } from 'react';
import UserList from './UserList';

function App() {
  const users = [
    {
      id: 1,
      username: 'subin',
      email: 'subin@example.com'
    },
    {
      id: 2,
      username: 'user1',
      email: 'user1@example.com'
    },
    {
      id: 3,
      username: 'user2',
      email: 'user2@example.com'
    }
  ];

  const nextId = useRef(4);
  const onCreate = () => {

    // ๋ฐฐ์ด์ ์๋ก์ด ํญ๋ณต ์ถ๊ฐํ๋ ๋ก์ง ์๋ต

    nextId.current += 1;
  };
  return <UserList users={users} />;
}

export default App;
```

import React, { useRef } from 'react';
**: useRef ํจ์๋ฅผ ๋ถ๋ฌ์จ๋ค.**

const nextId = useRef(4);
**: ๋ฐฐ์ด์ ๊ณ ์ ๊ฐ ๋ณ์๋ก nextId๋ฅผ ์ค์ ํด์ฃผ๊ณ ,
useRef() ํ๋ผํ๋ฏธํฐ๋ก ๋ค์ id๊ฐ ๋  ์ซ์ 4๋ฅผ ๋ฃ์ด์ค๋ค.
ํ๋ผ๋ฏธํฐ ๊ฐ์ ๋ฃ์ด์ฃผ๋ฉด ํด๋น ๊ฐ์ด ๋ณ์์ current ๊ฐ์ด ๋๋ค.
๊ทธ๋ฆฌ๊ณ  nextId ๋ณ์๋ฅผ ์์ ํ๊ฑฐ๋ ์กฐํ๋ ค๋ฉด .current ๊ฐ์ ์์ ํ๊ฑฐ๋ ์กฐํํ๋ค.**

nextId.current += 1;
**: ๋ณ์์ 1์ฉ ๋ํ์ฌ ์๋ฐ์ดํธ๋ฅผ ํ๋ค.**

---

### ๊ณต์๋ฌธ์์์ ๋งํ๋ Ref๋ฅผ ์ฌ์ฉํด์ผ ํ  ๋

Ref์ ๋ฐ๋์งํ ์ฌ์ฉ ์ฌ๋ก๋ ๋ค์๊ณผ ๊ฐ์ต๋๋ค.

- ํฌ์ปค์ค, ํ์คํธ ์ ํ์์ญ, ํน์ ๋ฏธ๋์ด์ ์ฌ์์ ๊ด๋ฆฌํ  ๋.
- ์ ๋๋ฉ์ด์์ ์ง์ ์ ์ผ๋ก ์คํ์ํฌ ๋.
- ์๋ ํํฐ DOM ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ React์ ๊ฐ์ด ์ฌ์ฉํ  ๋.

์ ์ธ์ ์ผ๋ก ํด๊ฒฐ๋  ์ ์๋ ๋ฌธ์ ์์๋ **ref ์ฌ์ฉ์ ์ง์**ํ์ธ์.

์๋ฅผ ๋ค์ด, Dialog ์ปดํฌ๋ํธ์์ open()๊ณผ close() ๋ฉ์๋๋ฅผ ๋๋ ๋์ , isOpen์ด๋ผ๋ prop์ ๋๊ฒจ์ฃผ์ธ์.

---

๐ ์ฐธ๊ณ ์๋ฃ
<br>
[![useRef_1](https://img.shields.io/badge/useRef-E8E8E8.svg?style=for-the-badge&logo=useRef&logoColor=white)](https://yoonjong-park.tistory.com/entry/React-useRef-%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94%EA%B0%80)
<br>
[![useRef_2](https://img.shields.io/badge/useRef_2-E8E8E8.svg?style=for-the-badge&logo=useRef_2&logoColor=white)](https://velog.io/@jinyoung985/React-useRef%EB%9E%80)
