# 🌟 Learned #8

# 🔶<props>

> props
> : 부모 Component에서 내려오는 모든 데이터
> => 우리가 내려준 데이터는 "Props객체 안에 이렇게 존재하는구나"를 알 수 있음.

```
function Mother() {
  const name = "홍부인";
  return <Child Mothername={name} />;
  //👆부모컴포넌트에서 자식컴포넌트로 props를 내려주는 방법
}

function Child(props) {
              //👆(props)부분은 'props로 네임을 전달했다.'라고 함
  console.log(props); //개발자도구에서 props가 잘 됐는지 콘솔에 찍어보기
  return <div>{props.Mothername}</div>;
    //👆자식컴포넌트에서 받아온 데이터에 접근해서 사용하는 방법
}
```

꼭 'props'라고 이름을 지어줘야할까?
=> 코드의 가독성을 위해 'Props'라고 이름을 주는 것뿐, 의미없는 변수 이름 'aaa'로도 가능하다.

## 🔹Props의 특성 중 알아야 할 한가지❗

Props는 오직 '부모Component에서 자식Component방향으로만' Props를 전달 할 수 있다.

## 🔹props : 부모 Component에서 내려오는 모든 데이터

=> 우리가 내려준 데이터는 "Props객체 안에 이렇게 존재하는구나"를 알 수 있음.

> Children ?
> Component 사이에 정보를 입력하는 방식으로 전달.
> Layout 이라는 Component 툴을 만들 때 자주 사용함.

```
function User(props){
return <div>props.children</div>;
}
//(props)를 하고, 밑에 props.children을 해주어야 밑 코드에서 User태그를 불러올 수 있음.

function App() {
return <User>안녕하세요</User>;
}

```

## \* 구조분해할당을 props에 적용하면 props에서 값을 가져올 때 더 간편하면서 가독성을 높일 수 있음.

## 🔹<props의 형태>

```
function 객체이름(props) {
return <div>{props.객체이름}</div>
}
<자바스크립트의 구조분해할당을 이용한 props의 형태>

function 객체({title}) {   //중괄호안에 객체의 Key name 적어주기
return <div>{title}</div>
}
.
.
//구조분해할당을 하지 않았다면, props.title로 값에 접근했을 것임
```

Props를 활용할 때 이 Props를 받아오는 값에 Default Props라는 것을 설정해 줄 수 있음.
Props 중에는 자주 받거나 무조건 받아야하는 Props들이 있음
-> 값이 없으면 문제가 되거나, UX가 어색해지는 경우
ex) 로그인이 완료되기 전까지 내 이름을 받아 오지 않는데 '\_\_\_\_'님 안녕하세요! < 이런 경우.

## 🔹<Default Props의 형태>

```
Child.defaultProps={
name: '기본 이름'
}
<구조분해할당을 이용해 객체에 직접 접근한 Default Props의 형태>

function Child({name="기본이름"}) {
return <div>내 이름은 {name} 입니다. </div>
}
```

부모 Component에서 Props가 내려오게 되면 Defualt Porps의 값은 사라지고 내려받은 props로 값이 대체된다.

---
  ## 🔹🌟 Props Drilling

> _**Prop Drilling?**_
> Prop Drilling 은 props를 오로지 하위(자식) 컴포넌트로 전달하는 용도로만 쓰이는 컴포넌트들을 거치면서 React Component 트리의 한 부분에서 다른 부분으로 데이터를 전달하는 과정입니다.

> ### 🌱뭐가 문제인가?
>
> 우선 Prop Drilling 은 문제가 되지 않습니다. prop 전달이 3~5개 정도의 컴포넌트라면 말이죠. Component들이 복잡해 질수록 Props Drilling이 문제가 되는 상황이 있습니다.
> 하지만 prop 전달이 10개, 15개 같이 더 많은 과정을 거치게 된다면 어떻게 될까요? 코드를 읽을 때 해당 prop을 추적하기 힘들어집니다.
> 그렇기 때문에 유지보수도 더욱 어려워집니다.

> ### 🌱그럼 어떻게 해야 할까?
>
> 과도한 Prop Drilling를 피하기 위해서는 여러 방법이 있습니다.

#### 1. 전역 상태관리 라이브러리 사용

redux, MobX, recoil 등을 사용하여 해당 값이 필요한 컴포넌트에서 직접 불러서 사용할 수 있습니다.
여기서 궁금해하시는 분들이 계실겁니다.

> Store와 연결되어 있는 부분을 따로 빼고 싶은데요?

해당 질문에 대한 답은 두 번째 방법에 있습니다.

#### 2. children 을 적극적으로 사용하는 것입니다.

```
import React from "react";
import "./styles.css";

export default function App() {
  const content = "Who needs me?";
 return (
    <div className="App">
      <FirstComponent>
        <SecondComponent>
          <ThirdComponent>
            <ComponentNeedingProps content={content}  />
          </ThirdComponent>
        </SecondComponent>
      </FirstComponent>
    </div>
  );
}

function FirstComponent({ children }) {
  return (
    <div>
      <h3>I am the first component</h3>;
     { children }
    </div>
  );
}

function SecondComponent({ children }) {
  return (
    <div>
      <h3>I am the second component</h3>;
     {children}
    </div>
  );
}

function ThirdComponent({ children }) {
  return (
    <div>
      <h3>I am the third component</h3>
        {children}
    </div>
  );
}

function ComponentNeedingProps({ content }) {
  return <h3>{content}</h3>
}
```

이렇게 리팩토링을 진행한다면 하나의 컴포넌트에서 값을 관리하고, 그 값을 하위요소로 전달할 때 전혀 코드의 추적이 어려워지지 않습니다.
  
---
  
## 🔹🌟 PropTypes

**PropTypes** 는 전달받은 데이터의 유효성을 검증하기 위해서 다양한 유효성 검사기(Validator)를 내보냅니다. prop에 유효하지 않은 값이 전달 되었을 때, 경고문이 JavaScript 콘솔을 통해 보일 것입니다. propTypes는 성능상의 이유로 개발 모드(Development mode) 에서만 확인될 것입니다.

Props의 타입이 어떤 타입인지 지정되지 않다보면 여러가지 문제들이 발생할 수 있다.
우리는 이 Props가 반드시 문자 열이라는 의도로 작성을 했지만 타입이 명확하게 지정되어 있지 않기 때문에 사용하는 것에서 또는 같이 코드를 작성하는 동료 개발자의 수정에 의해서 우리는 문자열로만 들어올 거라고 생각하고 작성했는데 숫자값이 들어온다 거나 하는 상황들이 충분히 발생할 수 있다. --> 이런 상황들이 버그를 일으킬 수 있다.

==>>타입마다 해당 타입에만 적용할 수 있는 메소드들(Number(), String() 등)이 있는데 타입이 정해져 있지 않으면 그 해당 타입에 사용할 수 없는 메소드들을 만나서 에러를 일으키곤 함. 그래서 Props의 Type을 검사할 수 있는 PropTypes은 중요하다 !

---

💟 참고자료
<br>
[![Prop_Drilling](https://img.shields.io/badge/Prop_Drilling-E8E8E8.svg?style=for-the-badge&logo=Prop_Drilling&logoColor=white)](https://slog.website/post/13)
<br>
[![PropTypes](https://img.shields.io/badge/PropTypes-E8E8E8.svg?style=for-the-badge&logo=PropTypes&logoColor=white)](https://ko.reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper)
<br>
[![Hook](https://img.shields.io/badge/Hook-E8E8E8.svg?style=for-the-badge&logo=Hook&logoColor=white)](https://ko.reactjs.org/docs/hooks-overview.html)
