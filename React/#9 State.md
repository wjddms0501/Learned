# 🌟 Learned #9

# 🔶 State

> State ?
> Component 내부에서 바뀔 수 있는 값, State를 사용할 때는 'useState'라는 것을 사용

> 🌞우리가 State를 이용해야 하는 이유.
> 우리가 배웠던 Component에는 LifeCycle이라는 개념이 있고 LifeCycle에 따라서 이 화면이 값이 변했을 때 그 변화된 값을 화면에 다시 리렌더링 >시켜주기 위한 조건들이 있다.
> 그 조건들 중 하나가 State가 변경되었을 때이다.
> let으로 선언해서 그 값을 새로운 값에 할당시켜 줄 수는 있지만, React에 의하면 변경된 값이 화면에 바로 반영되지 않는다. -> "State가 바뀌었다고 >인식하지 못하기 때문"
> 그래서 React에서 변화를 감지하고 화면을 즉시 리렌더링 시켜주기 위해서 State를 이용해야한다.

## 🔹<useState를 이용해서 State를 생성하는 코드>

```
const[Value, setValue]=useState(초기값)
```

빈배열의 첫번째 자리(Value)에는 State의 이름이 들어감.
두번째 자리(serValue)에는 set을 붙이고 State의 이름을 붙이게 되는데 첫번째 자리에서 선언했던 State의 이름. / State를 변경할 때 사용하는 함수.

useState에 괄화 안의 인자에는 State의 원하는 초기값(=initialState).

State는 새로고침하면 다시 초기값으로 바뀜.

## 🔹<🌟더 알아보면 좋은 키워드🌟>

> `Hook`?
> React에서만 제공하는 React에서만 존재하는 개념이자 기능(Hook은 함수 컴포넌트에서 React state와 생명주기 기능(lifecycle features)을 “연동(hook >into)“할 수 있게 해주는 함수)
> React에서 굉장히 중요한 개념❗

## 🔹<📌더 알아보면 좋은 내용들📌>

🔍Q1. 우리가 배운 useState외에도 다른 Hook들은 무엇이 있을까?

useEffect : 함수 컴포넌트 내에서 이런 side effects를 수행할 수 있게 해줍니다. React class의 componentDidMount 나 componentDidUpdate, componentWillUnmount와 같은 목적으로 제공되지만, 하나의 API로 통합된 것이다.
useContext : 컴포넌트를 중첩하지 않고도 React context를 구독할 수 있게 해준다.
useReducer : 복잡한 컴포넌트들의 state를 reducer로 관리할 수 있게 해준다.
이 외에도 useMemo, useCallback, useRef, useImperativeHandle, useDebugValue 등이 있다.
🔍Q2. State를 선언해 줄 때 사용한 const는 변경할 수 없는 상수인데 어떻게 State를 이용해서 값을 변경할 수 있었을까?

useState로 상태가 업데이트 될때, state값이 변경되는 것이 아니라, 재렌더링이 일어나게 되고 state는 항상 최신 상태의 값을 사용하기 때문이다.
이전의 state 변수는 컴포넌트 함수가 실행되면서 매번 새로운 const 변수가 실행된다.const로 선언함으로 state 변수를 직접 수정하는 것을 방지하고, setState를 사용하게 하기 위함이 const로 선언되는 이유이다.
🔍Q3. Component가 리렌더링 되는 조건에는 어떤것들이 있을까?

1. 자신의 상태가 변경될 때(state 변경)
2. 부모 컴포넌트가 리렌더링 될 때
3. 자신이 전달받은 props가 변경될 때(props)
4. forceUpdate 함수가 실행될 때

## 🔹<button에서의 useState>

```
function App() {
function onClickHandler() {
console.log("hello, button")
}
return (
<div>
  <button onClick={onClickHandler}>버튼</button>
</div>
);
}
```

<State를 이벤트 핸들러와 연결>

```
// src/App.js
import React, { useState } from "react";

function App() {
  function onClickHandler() {
    setName("누렁이");
  }
  const [name, setName] = useState("길동이");
  return (
    <div>
      {name}
      <button onClick={onClickHandler}>버튼</button>
    </div>
  );
}

export default App;
```

## 🔹<input에서의 useState>

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

## 🔹<State를 핸들러와 연결>

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

💟 참고자료
<br>
[![값이 변하는 State를 변할 수 없는 상수 const에 선언하는 이유](https://img.shields.io/badge/값이 변하는 State를 변할 수 없는 상수 const에 선언하는 이유-E8E8E8.svg?style=for-the-badge&logo=값이 변하는 State를 변할 수 없는 상수 const에 선언하는 이유&logoColor=white)](https://dudghsx.tistory.com/18)
