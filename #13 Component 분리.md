# 🌟 Learned #13

# 🔶 Component 분리

## 🔹추가(➕) & 삭제(➖)버튼 만들고 Component 분리하기

(표시범위 기호)
📍👇 여기부터 📍👆여기까지

\*📍👉 한 줄

> ### 🔹🌟<1개씩 추가하기 버튼 핸들러>

```
import React, { useState } from "react";
import "./App.css"; // 🔥 반드시 App.css 파일을 import 해줘야 합니다.

📍👇function User(props) {
  return (
    <div className="square-style">
      {props.user.age}살 - {props.user.name}
    </div>
  );
📍👆}

const App = () => {
 📍👇const [users, setUsers] = useState([
    { id: 1, age: 30, name: "송중기" },
    { id: 2, age: 24, name: "송강" },
    { id: 3, age: 21, name: "김유정" },
    { id: 4, age: 29, name: "구교환" },
  ]);
  const [name, setName] = useState("")
  📍👆const [age, setAge] = useState("")

  📍👇const addUserHandler=()=>{
    const newUser={
      id=users.length+1,
      age:age,
      name:name
    }
    setUsers([...users.nesUser])
  📍👆}

  return (
    📍👇<div>
    <div className="app-style">
      {users.map((user) => {
        return (<User user={user} key={user.id}></User>;
      )})}
      📍👆</div>
      <input
        value={name}
        placeholder="이름을 입력해주세요"
        // 인풋 이벤트로 들어온 입력 값을 name의 값으로 업데이트
        onChange={(e) => setName(e.target.value)}
      />
      <input
        value={age}
        placeholder="나이를 입력해주세요"
        // 인풋 이벤트로 들어온 입력 값을 age의 값으로 업데이트
        onChange={(e) => setAge(e.target.value)}
      />
      📍👉<button onClick={addUserHandler}>추가하기</button>
    </div>
  );
};

export default App;
```

<br>
<br>

> ### 🔹🌟<각 버튼마다 삭제하기 버튼 핸들러>

```
import React, { useState } from "react";
import "./App.css"; // 🔥 반드시 App.css 파일을 import 해줘야 합니다.

function User(props) {
  return (
    <div className="square-style">
      {props.user.age}살 - {props.user.name}
      📍👉<button onClick={()=>{props.handleDelete(props.user.id)}}>삭제하기</button>
    {/*👆삭제버튼 */}
    </div>
  );
}

const App = () => {
  const [users, setUsers] = useState([
    { id: 1, age: 30, name: "송중기" },
    { id: 2, age: 24, name: "송강" },
    { id: 3, age: 21, name: "김유정" },
    { id: 4, age: 29, name: "구교환" },
  ]);
  const [name, setName] = useState("")
  const [age, setAge] = useState("")

  const addUserHandler=()=>{
    const newUser={
      id=users.length+1,
      age:age,
      name:name
    }
    setUsers([...users.nesUser])
  }

  📍👇const deleteUserHandler=(id) => {
    const newUserList = users.filter((user)=>user.id!==id)
  }
  //👆각각의 유저 아이디가 지금 내가 설정한 아이디와 같지 않으면 그것만 filter해서 새로운 유저리스트를 만들어라
setUsers(newUserList)
//또는
//const deleteUserHandler=(id) => {
//const newUserList =
//setUsers(users.filter((user)=>user.id!==id))
//}📍👆

  return (
    <div>
      <div className="app-style">
        {users.map((user) => {
         return <User user={user} key={user.id}></User>;
        })}
      </div>

      📍👇 //위와 같으나 삭제버튼의 코드를 나타낸 것<div>
     //<div className="app-style">
        //{users.map((user) => {
         //return (<User handleDelet={deleteUserHandler} user={user} //key={user.id}></User>;
        //user에다가 delete 함수 넣어주고 deleteUserHandler를 props로 넘기기
        //)})}
    //</div>📍👆

      <input
        value={name}
        placeholder="이름을 입력해주세요"
        // 인풋 이벤트로 들어온 입력 값을 name의 값으로 업데이트
        onChange={(e) => setName(e.target.value)}
      />
      <input
        value={age}
        placeholder="나이를 입력해주세요"
        // 인풋 이벤트로 들어온 입력 값을 age의 값으로 업데이트
        onChange={(e) => setAge(e.target.value)}
      />
      <button onClick={addUserHandler}>추가하기</button>
    </div>
  );
};

export default App;
```

<br>
<br>
> ### 🔹🌟<Component 분리하기>

```
import React, { useState } from "react";
import "./App.css"; // 🔥 반드시 App.css 파일을 import 해줘야 합니다.

//버튼 Component
//이렇게 Component를 분리해주면 추가하기는 초록, 삭제는 빨강처럼
//간단히 props에 색을 넘겨주는 것만으로도 버튼의 색설정을 할 수 있다.
📍👇function CustomButton(props){
  const {color,onClick,children} = props //구조 분해 할당
  if(color){
    return <button
    style = {{backgroundColor:color, color:"white"}}
    onClick = {onClick}>{children}</button>
  }
  return <button onClick = {onClick}>{children}</button>
}
//만약에 props에 color로 받아온 값이 있으면 color를 적용한 버튼을 만들어주고
//그게 아니면 그냥 버튼을 줄 거다.
//무조건 color가 있는 버튼을 만들어주고 싶다면 if문을 지우면된다.
📍👆


function User(props) {
  return (
    <div className="square-style">
      {props.user.age}살 - {props.user.name}
      📍👉<CustomButton color="red" onClick={()=>{props.handleDelete(props.user.id)}}>삭제하기</CustomButton>
    {/*👆CustomButton의 props로 color 넘기기 */}
    {/*👆삭제버튼 */}
    </div>
  );
}

const App = () => {
  const [users, setUsers] = useState([
    { id: 1, age: 30, name: "송중기" },
    { id: 2, age: 24, name: "송강" },
    { id: 3, age: 21, name: "김유정" },
    { id: 4, age: 29, name: "구교환" },
  ]);
  const [name, setName] = useState("")
  const [age, setAge] = useState("")

  const addUserHandler=()=>{
    const newUser={
      id=users.length+1,
      age:age,
      name:name
    }
    setUsers([...users.nesUser])
  }

  const deleteUserHandler=(id) => {
    const newUserList = users.filter((user)=>user.id!==id)
  }
  //👆각각의 유저 아이디가 지금 내가 설정한 아이디와 같지 않으면 그것만 filter해서 새로운 유저리스트를 만들어라
setUsers(newUserList)
//또는
//const deleteUserHandler=(id) => {
//const newUserList =
//setUsers(users.filter((user)=>user.id!==id))
//}

  return (
    <div>
      <div className="app-style">
        {users.map((user) => {
         return <User user={user} key={user.id}></User>;
        })}
      </div>

      //위와 같으나 삭제버튼의 코드를 나타낸 것<div>
     //<div className="app-style">
        //{users.map((user) => {
         //return (<User handleDelet={deleteUserHandler} user={user} //key={user.id}></User>;
        //user에다가 delete 함수 넣어주고 deleteUserHandler를 props로 넘기기
        //)})}
    //</div>

      <input
        value={name}
        placeholder="이름을 입력해주세요"
        // 인풋 이벤트로 들어온 입력 값을 name의 값으로 업데이트
        onChange={(e) => setName(e.target.value)}
      />
      <input
        value={age}
        placeholder="나이를 입력해주세요"
        // 인풋 이벤트로 들어온 입력 값을 age의 값으로 업데이트
        onChange={(e) => setAge(e.target.value)}
      />
      📍👉<CustomButton color="green" onClick={addUserHandler}>추가하기</CustomButton>
    </div>
  );
};

export default App;
```

# **🔷`🔑'key={...}'_ 가 중요한 이유`**

> 'key={...}' 값을 넣지 않으면 개발자도구에서
> "Each child in a list should have a unique "key" prop."
> (모든 child는 unique한 key값을 props로 가져야된다.) 라는 에러가 뜬다.
> 그래서 React에서는 map을 사용해서 Component를 반복렌더링할 때, 반드시 Component의 key를 넣어주어야 한다.
> => **React에서 Component배열을 렌더링할 때 각각의 원소에서 변동이 있는지 >알아내려고 사용하기 때문❗**

> **만약 `key가 없다`면?**
> 위에 말한 오류가 뜨며, React는 가상Dom을 비교하는 과정에서 배열을 순차적으로 비교하면서 변화를 감지하려고 한다. 하지만 key가 있으면 어떤 변화가 일어났는지, 더 빠르게 알아낼 수 있다. 즉 **key값을 넣어주어야 React의 성능이 최적화가 된다.**

---

🎲Q1. age가 25살 이상인 user는 제외하고 렌더링하기
: age가 25미민인 user는 화면에 렌더링해주고, 그것이 아닐 때는 아무것도 렌더링하지 않으면 됨. "null을 return 하면 됨❗"
null : 값이 없다고 하는 것을 개발자가 의도적으로 표현하고자 하는 데이터 형태이자 값

```
<div>
      <div className="app-style">
        {users.map((user) => {
          if(user.age<25){
         return (<User handleDelet={deleteUserHandler} user={user} key={user.id}></User>;
        )
      } else {
        return null;
      }
        })}
    </div>
```

## 🔹컴포넌트 분리하기

### 🔹👀App Component와 User Component, Button Component가 모두 App.js파일 한 곳에 작성 되어 있기 때문에 발생하는 문제들

`첫번째`, App.js파일의 역할이 명확하지 않다.
`두번째`, Component 분리를 통해서 가독성을 높였지만 두 Component의 사이즈가 커지거나 또 다른 Component를 작성하게 되면 가독성은 금방 떨어진다.
`세번째`, 현재 구조에서 User Component와 Button Component가 어디에 작성되어있는지 찾기가 힘들다. 특히 작성자가 아닌 다른 개발자가 App.js파일을 보고 User Component와 Button Component가 여기 있을거라 유추하기 어렵다.
==> **'그래서 일반적으로 계속 여러번 렌더링해서 기능을 재사용하는 Component들은 따로 분리해서 사용한다.'**

🌟 참고 : 하나의 폴더 안에 모든 Component를 만들어서 관리하면 시간이 흐를수록 Component가 많아져서 원하는 Component를 찾기가 어렵다.
**연관된 Component끼리 폴더를 만들어서 관리하는 것이 Component를 찾기에 수월하다.**

### 🔹Component 분리하기

1. VSCode 왼쪽 해당 폴더 src 밑에 새폴더로 components 폴더를 만든다.
2. components 폴더안에 CustomButton.js파일을 만들어준다.
3. 작성한 App.js에서 CustomButton 부분을 잘라서 가져온다.
4. **CustomButton를 분리할 경우 외부에서 쓰기 위해** CustomButton 코드 밑에
   **export default CustomButton** 코드를 추가 후 저장한다.
5. App.js로 돌아가서 내보냈던 CustomButton 컴포넌트를 사용하기 위해
   **import CustomButton from "./components/CustomButton"**; 를 추가한다.
   '.' 점 1개는 이 위치에서 상대경로로 어디에 있다. 는 뜻이고
   "./components/CustomButton"는 App.js에서 지금 CustomButton울 가져오겠다는 뜻.
