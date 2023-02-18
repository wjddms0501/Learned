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

💟 참고자료
<br>
[![Prop Drilling](https://img.shields.io/badge/Prop Drilling-E8E8E8.svg?style=for-the-badge&logo=Prop Drilling&logoColor=white)](https://slog.website/post/13)
<br>
[![PropTypes](https://img.shields.io/badge/PropTypes-E8E8E8.svg?style=for-the-badge&logo=PropTypes&logoColor=white)](https://ko.reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper)
<br>
[![Hook](https://img.shields.io/badge/Hook-E8E8E8.svg?style=for-the-badge&logo=Hook&logoColor=white)](https://ko.reactjs.org/docs/hooks-overview.html)
