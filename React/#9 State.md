# ๐ Learned #9

# ๐ถ State

> State ?
> Component ๋ด๋ถ์์ ๋ฐ๋ ์ ์๋ ๊ฐ, State๋ฅผ ์ฌ์ฉํ  ๋๋ 'useState'๋ผ๋ ๊ฒ์ ์ฌ์ฉ

> ๐์ฐ๋ฆฌ๊ฐ State๋ฅผ ์ด์ฉํด์ผ ํ๋ ์ด์ .
> ์ฐ๋ฆฌ๊ฐ ๋ฐฐ์ ๋ Component์๋ LifeCycle์ด๋ผ๋ ๊ฐ๋์ด ์๊ณ  LifeCycle์ ๋ฐ๋ผ์ ์ด ํ๋ฉด์ด ๊ฐ์ด ๋ณํ์ ๋ ๊ทธ ๋ณํ๋ ๊ฐ์ ํ๋ฉด์ ๋ค์ ๋ฆฌ๋ ๋๋ง >์์ผ์ฃผ๊ธฐ ์ํ ์กฐ๊ฑด๋ค์ด ์๋ค.
> ๊ทธ ์กฐ๊ฑด๋ค ์ค ํ๋๊ฐ State๊ฐ ๋ณ๊ฒฝ๋์์ ๋์ด๋ค.
> let์ผ๋ก ์ ์ธํด์ ๊ทธ ๊ฐ์ ์๋ก์ด ๊ฐ์ ํ ๋น์์ผ ์ค ์๋ ์์ง๋ง, React์ ์ํ๋ฉด ๋ณ๊ฒฝ๋ ๊ฐ์ด ํ๋ฉด์ ๋ฐ๋ก ๋ฐ์๋์ง ์๋๋ค. -> "State๊ฐ ๋ฐ๋์๋ค๊ณ  >์ธ์ํ์ง ๋ชปํ๊ธฐ ๋๋ฌธ"
> ๊ทธ๋์ React์์ ๋ณํ๋ฅผ ๊ฐ์งํ๊ณ  ํ๋ฉด์ ์ฆ์ ๋ฆฌ๋ ๋๋ง ์์ผ์ฃผ๊ธฐ ์ํด์ State๋ฅผ ์ด์ฉํด์ผํ๋ค.

## ๐น<useState๋ฅผ ์ด์ฉํด์ State๋ฅผ ์์ฑํ๋ ์ฝ๋>

```
const[Value, setValue]=useState(์ด๊ธฐ๊ฐ)
```

๋น๋ฐฐ์ด์ ์ฒซ๋ฒ์งธ ์๋ฆฌ(Value)์๋ State์ ์ด๋ฆ์ด ๋ค์ด๊ฐ.
๋๋ฒ์งธ ์๋ฆฌ(serValue)์๋ set์ ๋ถ์ด๊ณ  State์ ์ด๋ฆ์ ๋ถ์ด๊ฒ ๋๋๋ฐ ์ฒซ๋ฒ์งธ ์๋ฆฌ์์ ์ ์ธํ๋ State์ ์ด๋ฆ. / State๋ฅผ ๋ณ๊ฒฝํ  ๋ ์ฌ์ฉํ๋ ํจ์.

useState์ ๊ดํ ์์ ์ธ์์๋ State์ ์ํ๋ ์ด๊ธฐ๊ฐ(=initialState).

State๋ ์๋ก๊ณ ์นจํ๋ฉด ๋ค์ ์ด๊ธฐ๊ฐ์ผ๋ก ๋ฐ๋.

## ๐น<๐๋ ์์๋ณด๋ฉด ์ข์ ํค์๋๐>

> `Hook`?
> React์์๋ง ์ ๊ณตํ๋ React์์๋ง ์กด์ฌํ๋ ๊ฐ๋์ด์ ๊ธฐ๋ฅ(Hook์ ํจ์ ์ปดํฌ๋ํธ์์ React state์ ์๋ช์ฃผ๊ธฐ ๊ธฐ๋ฅ(lifecycle features)์ โ์ฐ๋(hook >into)โํ  ์ ์๊ฒ ํด์ฃผ๋ ํจ์)
> React์์ ๊ต์ฅํ ์ค์ํ ๊ฐ๋โ

## ๐น<๐๋ ์์๋ณด๋ฉด ์ข์ ๋ด์ฉ๋ค๐>

๐Q1. ์ฐ๋ฆฌ๊ฐ ๋ฐฐ์ด useState์ธ์๋ ๋ค๋ฅธ Hook๋ค์ ๋ฌด์์ด ์์๊น?

useEffect : ํจ์ ์ปดํฌ๋ํธ ๋ด์์ ์ด๋ฐ side effects๋ฅผ ์ํํ  ์ ์๊ฒ ํด์ค๋๋ค. React class์ componentDidMount ๋ componentDidUpdate, componentWillUnmount์ ๊ฐ์ ๋ชฉ์ ์ผ๋ก ์ ๊ณต๋์ง๋ง, ํ๋์ API๋ก ํตํฉ๋ ๊ฒ์ด๋ค.
useContext : ์ปดํฌ๋ํธ๋ฅผ ์ค์ฒฉํ์ง ์๊ณ ๋ React context๋ฅผ ๊ตฌ๋ํ  ์ ์๊ฒ ํด์ค๋ค.
useReducer : ๋ณต์กํ ์ปดํฌ๋ํธ๋ค์ state๋ฅผ reducer๋ก ๊ด๋ฆฌํ  ์ ์๊ฒ ํด์ค๋ค.
์ด ์ธ์๋ useMemo, useCallback, useRef, useImperativeHandle, useDebugValue ๋ฑ์ด ์๋ค.
๐Q2. State๋ฅผ ์ ์ธํด ์ค ๋ ์ฌ์ฉํ const๋ ๋ณ๊ฒฝํ  ์ ์๋ ์์์ธ๋ฐ ์ด๋ป๊ฒ State๋ฅผ ์ด์ฉํด์ ๊ฐ์ ๋ณ๊ฒฝํ  ์ ์์์๊น?

useState๋ก ์ํ๊ฐ ์๋ฐ์ดํธ ๋ ๋, state๊ฐ์ด ๋ณ๊ฒฝ๋๋ ๊ฒ์ด ์๋๋ผ, ์ฌ๋ ๋๋ง์ด ์ผ์ด๋๊ฒ ๋๊ณ  state๋ ํญ์ ์ต์  ์ํ์ ๊ฐ์ ์ฌ์ฉํ๊ธฐ ๋๋ฌธ์ด๋ค.
์ด์ ์ state ๋ณ์๋ ์ปดํฌ๋ํธ ํจ์๊ฐ ์คํ๋๋ฉด์ ๋งค๋ฒ ์๋ก์ด const ๋ณ์๊ฐ ์คํ๋๋ค.const๋ก ์ ์ธํจ์ผ๋ก state ๋ณ์๋ฅผ ์ง์  ์์ ํ๋ ๊ฒ์ ๋ฐฉ์งํ๊ณ , setState๋ฅผ ์ฌ์ฉํ๊ฒ ํ๊ธฐ ์ํจ์ด const๋ก ์ ์ธ๋๋ ์ด์ ์ด๋ค.
๐Q3. Component๊ฐ ๋ฆฌ๋ ๋๋ง ๋๋ ์กฐ๊ฑด์๋ ์ด๋ค๊ฒ๋ค์ด ์์๊น?

1. ์์ ์ ์ํ๊ฐ ๋ณ๊ฒฝ๋  ๋(state ๋ณ๊ฒฝ)
2. ๋ถ๋ชจ ์ปดํฌ๋ํธ๊ฐ ๋ฆฌ๋ ๋๋ง ๋  ๋
3. ์์ ์ด ์ ๋ฌ๋ฐ์ props๊ฐ ๋ณ๊ฒฝ๋  ๋(props)
4. forceUpdate ํจ์๊ฐ ์คํ๋  ๋

## ๐น<button์์์ useState>

```
function App() {
function onClickHandler() {
console.log("hello, button")
}
return (
<div>
  <button onClick={onClickHandler}>๋ฒํผ</button>
</div>
);
}
```

<State๋ฅผ ์ด๋ฒคํธ ํธ๋ค๋ฌ์ ์ฐ๊ฒฐ>

```
// src/App.js
import React, { useState } from "react";

function App() {
  function onClickHandler() {
    setName("๋๋ ์ด");
  }
  const [name, setName] = useState("๊ธธ๋์ด");
  return (
    <div>
      {name}
      <button onClick={onClickHandler}>๋ฒํผ</button>
    </div>
  );
}

export default App;
```

## ๐น<input์์์ useState>

```
// src/App.js
import React, { useState } from "react";

const App() => {
  const [Value, setValue] = useState("");
  return (
    <div>
      {name}
      <input type="text" />
    </div>
  );
};

export default App;
```

## ๐น<State๋ฅผ ํธ๋ค๋ฌ์ ์ฐ๊ฒฐ>

```
// src/App.js
import React, { useState, value } from "react";

const App = () => {
  const [Value, setValue] = useState("");
  const onChangeHandler = (event) => {
    const inputValue = event.target.value;
    setValue(inputValue);
  };
  console.log(Value);
  return (
    <div>
      <input type="text" onChange={onChangeHandler} value={value} />
    </div>
  );
};

export default App;
```

---

๐ ์ฐธ๊ณ ์๋ฃ
<br>
[![๊ฐ์ด ๋ณํ๋ State๋ฅผ ๋ณํ  ์ ์๋ ์์ const์ ์ ์ธํ๋ ์ด์ ](https://img.shields.io/badge/๊ฐ์ด ๋ณํ๋ State๋ฅผ ๋ณํ  ์ ์๋ ์์ const์ ์ ์ธํ๋ ์ด์ -E8E8E8.svg?style=for-the-badge&logo=๊ฐ์ด ๋ณํ๋ State๋ฅผ ๋ณํ  ์ ์๋ ์์ const์ ์ ์ธํ๋ ์ด์ &logoColor=white)](https://dudghsx.tistory.com/18)
