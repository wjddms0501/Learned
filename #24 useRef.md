# 🌟 Learned #24

# 🔶 useRef

> `useRef`는 저장공간 또는 DOM요소에 접근하기 위해 사용되는 React Hook입니다.
> 여기서 Ref는 reference, 즉 **참조**를 뜻합니다.

우리가 자바스크립트를 사용 할 때에는, 우리가 특정 DOM 을 선택하기 위해서 querySelector 등의 함수를 사용합니다.

React를 사용하는 프로젝트에서도 가끔씩 DOM 을 직접 선택해야 하는 상황이 필요합니다. 그럴때 우리는 useRef라는 React Hook을 사용합니다.

useRef로 관리되는 값은 값이 변환되어도 리렌더링 되지 않습니다.

## useRef가 필요한 상황

### 1. 컴포넌트에 focus를 위치시킬 필요가 있는 경우.

-예를 들어, 값을 여러개 입력하고 첫 번째 칸으로 이동해야 하는 경우 필요하다.

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

      <button onClick={onReset}>초기화</button>
      <div>
        <b>내용: </b>
        {text}
      </div>
    </div>
  );
}

export default InputTest;
```

const nameInput = useRef();
**ㄴ Ref 객체를 만들어주고**

<input
  name="name"
  onChange={onChange}
  value={text}
  ref={nameInput}
/>
**ㄴ 선택하고 싶은 DOM에 속성으로 ref 값을 설정해준다.**

nameInput.current.focus();
**: Ref 객체의 current 값은 우리가 선택하고자 하는 DOM을 가리킨다.
그리고 포커싱을 해주는 DOM API focus() 를 호출한다.**

### 2. 속성 값을 초기화(clear)할 필요가 있는 경우.

-예를 들어, 카운터의 값을 0으로 초기화 할 필요가 있을 때. (ex.타이머 0으로 만들기)
-setInterval 이나 setTimeout과 같은 함수는 clear 시켜주지 않으면 메모리를 많이 소모하기 때문이다.

```
// App.js

const RSPfunction = () => {
  const [result, setResult] = useState('');
  const [imgCoord, setImgCoord] = useState(rspCoords.바위);
  const [score, setScore] = useState(0);
  const interval = useRef();

  useEffect(() => {
    interval.current = setInterval(changeHand, 100);
    return () => {
      clearInterval(interval.current);
    }
  }, [imgCoord]);
//  코드 생략
```

### 3. useRef로 컴포넌트 안의 변수 관리하기

-리 렌더링을 하지 않으면서 컴포넌트의 속성 정보를 조회 & 수정할 때

- useRef를 활용한 변수는 아래와 같은 곳에 쓰인다.
  -setTimeout, setInterval을 통해 만들어진 id
  -scroll 위치 -배열에 새 항목을 추가할 때 필요한 고유값 key

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

    // 배열에 새로운 항복 추가하는 로직 생략

    nextId.current += 1;
  };
  return <UserList users={users} />;
}

export default App;
```

import React, { useRef } from 'react';
**: useRef 함수를 불러온다.**

const nextId = useRef(4);
**: 배열의 고유값 변수로 nextId를 설정해주고,
useRef() 파라타미터로 다음 id가 될 숫자 4를 넣어준다.
파라미터 값을 넣어주면 해당 값이 변수의 current 값이 된다.
그리고 nextId 변수를 수정하거나 조회려면 .current 값을 수정하거나 조회한다.**

nextId.current += 1;
**: 변수에 1씩 더하여 업데이트를 한다.**

---

### 공식문서에서 말하는 Ref를 사용해야 할 때

Ref의 바람직한 사용 사례는 다음과 같습니다.

- 포커스, 텍스트 선택영역, 혹은 미디어의 재생을 관리할 때.
- 애니메이션을 직접적으로 실행시킬 때.
- 서드 파티 DOM 라이브러리를 React와 같이 사용할 때.

선언적으로 해결될 수 있는 문제에서는 **ref 사용을 지양**하세요.

예를 들어, Dialog 컴포넌트에서 open()과 close() 메서드를 두는 대신, isOpen이라는 prop을 넘겨주세요.

---

💟 참고자료
<br>
[![useRef_1](https://img.shields.io/badge/useRef-E8E8E8.svg?style=for-the-badge&logo=useRef&logoColor=white)](https://yoonjong-park.tistory.com/entry/React-useRef-%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94%EA%B0%80)
<br>
[![useRef_2](https://img.shields.io/badge/useRef_2-E8E8E8.svg?style=for-the-badge&logo=useRef_2&logoColor=white)](https://velog.io/@jinyoung985/React-useRef%EB%9E%80)
