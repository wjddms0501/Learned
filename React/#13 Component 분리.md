# π Learned #13

# πΆ Component λΆλ¦¬

## πΉμΆκ°(β) & μ­μ (β)λ²νΌ λ§λ€κ³  Component λΆλ¦¬νκΈ°

(νμλ²μ κΈ°νΈ)
ππ μ¬κΈ°λΆν° ππμ¬κΈ°κΉμ§

\*ππ ν μ€

> ### πΉπ<1κ°μ© μΆκ°νκΈ° λ²νΌ νΈλ€λ¬>

```
import React, { useState } from "react";
import "./App.css"; // π₯ λ°λμ App.css νμΌμ import ν΄μ€μΌ ν©λλ€.

ππfunction User(props) {
  return (
    <div className="square-style">
      {props.user.age}μ΄ - {props.user.name}
    </div>
  );
ππ}

const App = () => {
 ππconst [users, setUsers] = useState([
    { id: 1, age: 30, name: "μ‘μ€κΈ°" },
    { id: 2, age: 24, name: "μ‘κ°" },
    { id: 3, age: 21, name: "κΉμ μ " },
    { id: 4, age: 29, name: "κ΅¬κ΅ν" },
  ]);
  const [name, setName] = useState("")
  ππconst [age, setAge] = useState("")

  ππconst addUserHandler=()=>{
    const newUser={
      id=users.length+1,
      age:age,
      name:name
    }
    setUsers([...users.nesUser])
  ππ}

  return (
    ππ<div>
    <div className="app-style">
      {users.map((user) => {
        return (<User user={user} key={user.id}></User>;
      )})}
      ππ</div>
      <input
        value={name}
        placeholder="μ΄λ¦μ μλ ₯ν΄μ£ΌμΈμ"
        // μΈν μ΄λ²€νΈλ‘ λ€μ΄μ¨ μλ ₯ κ°μ nameμ κ°μΌλ‘ μλ°μ΄νΈ
        onChange={(e) => setName(e.target.value)}
      />
      <input
        value={age}
        placeholder="λμ΄λ₯Ό μλ ₯ν΄μ£ΌμΈμ"
        // μΈν μ΄λ²€νΈλ‘ λ€μ΄μ¨ μλ ₯ κ°μ ageμ κ°μΌλ‘ μλ°μ΄νΈ
        onChange={(e) => setAge(e.target.value)}
      />
      ππ<button onClick={addUserHandler}>μΆκ°νκΈ°</button>
    </div>
  );
};

export default App;
```

<br>
<br>

> ### πΉπ<κ° λ²νΌλ§λ€ μ­μ νκΈ° λ²νΌ νΈλ€λ¬>

```
import React, { useState } from "react";
import "./App.css"; // π₯ λ°λμ App.css νμΌμ import ν΄μ€μΌ ν©λλ€.

function User(props) {
  return (
    <div className="square-style">
      {props.user.age}μ΄ - {props.user.name}
      ππ<button onClick={()=>{props.handleDelete(props.user.id)}}>μ­μ νκΈ°</button>
    {/*πμ­μ λ²νΌ */}
    </div>
  );
}

const App = () => {
  const [users, setUsers] = useState([
    { id: 1, age: 30, name: "μ‘μ€κΈ°" },
    { id: 2, age: 24, name: "μ‘κ°" },
    { id: 3, age: 21, name: "κΉμ μ " },
    { id: 4, age: 29, name: "κ΅¬κ΅ν" },
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

  ππconst deleteUserHandler=(id) => {
    const newUserList = users.filter((user)=>user.id!==id)
  }
  //πκ°κ°μ μ μ  μμ΄λκ° μ§κΈ λ΄κ° μ€μ ν μμ΄λμ κ°μ§ μμΌλ©΄ κ·Έκ²λ§ filterν΄μ μλ‘μ΄ μ μ λ¦¬μ€νΈλ₯Ό λ§λ€μ΄λΌ
setUsers(newUserList)
//λλ
//const deleteUserHandler=(id) => {
//const newUserList =
//setUsers(users.filter((user)=>user.id!==id))
//}ππ

  return (
    <div>
      <div className="app-style">
        {users.map((user) => {
         return <User user={user} key={user.id}></User>;
        })}
      </div>

      ππ //μμ κ°μΌλ μ­μ λ²νΌμ μ½λλ₯Ό λνλΈ κ²<div>
     //<div className="app-style">
        //{users.map((user) => {
         //return (<User handleDelet={deleteUserHandler} user={user} //key={user.id}></User>;
        //userμλ€κ° delete ν¨μ λ£μ΄μ£Όκ³  deleteUserHandlerλ₯Ό propsλ‘ λκΈ°κΈ°
        //)})}
    //</div>ππ

      <input
        value={name}
        placeholder="μ΄λ¦μ μλ ₯ν΄μ£ΌμΈμ"
        // μΈν μ΄λ²€νΈλ‘ λ€μ΄μ¨ μλ ₯ κ°μ nameμ κ°μΌλ‘ μλ°μ΄νΈ
        onChange={(e) => setName(e.target.value)}
      />
      <input
        value={age}
        placeholder="λμ΄λ₯Ό μλ ₯ν΄μ£ΌμΈμ"
        // μΈν μ΄λ²€νΈλ‘ λ€μ΄μ¨ μλ ₯ κ°μ ageμ κ°μΌλ‘ μλ°μ΄νΈ
        onChange={(e) => setAge(e.target.value)}
      />
      <button onClick={addUserHandler}>μΆκ°νκΈ°</button>
    </div>
  );
};

export default App;
```

<br>
<br>
> ### πΉπ<Component λΆλ¦¬νκΈ°>

```
import React, { useState } from "react";
import "./App.css"; // π₯ λ°λμ App.css νμΌμ import ν΄μ€μΌ ν©λλ€.

//λ²νΌ Component
//μ΄λ κ² Componentλ₯Ό λΆλ¦¬ν΄μ£Όλ©΄ μΆκ°νκΈ°λ μ΄λ‘, μ­μ λ λΉ¨κ°μ²λΌ
//κ°λ¨ν propsμ μμ λκ²¨μ£Όλ κ²λ§μΌλ‘λ λ²νΌμ μμ€μ μ ν  μ μλ€.
ππfunction CustomButton(props){
  const {color,onClick,children} = props //κ΅¬μ‘° λΆν΄ ν λΉ
  if(color){
    return <button
    style = {{backgroundColor:color, color:"white"}}
    onClick = {onClick}>{children}</button>
  }
  return <button onClick = {onClick}>{children}</button>
}
//λ§μ½μ propsμ colorλ‘ λ°μμ¨ κ°μ΄ μμΌλ©΄ colorλ₯Ό μ μ©ν λ²νΌμ λ§λ€μ΄μ£Όκ³ 
//κ·Έκ² μλλ©΄ κ·Έλ₯ λ²νΌμ μ€ κ±°λ€.
//λ¬΄μ‘°κ±΄ colorκ° μλ λ²νΌμ λ§λ€μ΄μ£Όκ³  μΆλ€λ©΄ ifλ¬Έμ μ§μ°λ©΄λλ€.
ππ


function User(props) {
  return (
    <div className="square-style">
      {props.user.age}μ΄ - {props.user.name}
      ππ<CustomButton color="red" onClick={()=>{props.handleDelete(props.user.id)}}>μ­μ νκΈ°</CustomButton>
    {/*πCustomButtonμ propsλ‘ color λκΈ°κΈ° */}
    {/*πμ­μ λ²νΌ */}
    </div>
  );
}

const App = () => {
  const [users, setUsers] = useState([
    { id: 1, age: 30, name: "μ‘μ€κΈ°" },
    { id: 2, age: 24, name: "μ‘κ°" },
    { id: 3, age: 21, name: "κΉμ μ " },
    { id: 4, age: 29, name: "κ΅¬κ΅ν" },
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
  //πκ°κ°μ μ μ  μμ΄λκ° μ§κΈ λ΄κ° μ€μ ν μμ΄λμ κ°μ§ μμΌλ©΄ κ·Έκ²λ§ filterν΄μ μλ‘μ΄ μ μ λ¦¬μ€νΈλ₯Ό λ§λ€μ΄λΌ
setUsers(newUserList)
//λλ
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

      //μμ κ°μΌλ μ­μ λ²νΌμ μ½λλ₯Ό λνλΈ κ²<div>
     //<div className="app-style">
        //{users.map((user) => {
         //return (<User handleDelet={deleteUserHandler} user={user} //key={user.id}></User>;
        //userμλ€κ° delete ν¨μ λ£μ΄μ£Όκ³  deleteUserHandlerλ₯Ό propsλ‘ λκΈ°κΈ°
        //)})}
    //</div>

      <input
        value={name}
        placeholder="μ΄λ¦μ μλ ₯ν΄μ£ΌμΈμ"
        // μΈν μ΄λ²€νΈλ‘ λ€μ΄μ¨ μλ ₯ κ°μ nameμ κ°μΌλ‘ μλ°μ΄νΈ
        onChange={(e) => setName(e.target.value)}
      />
      <input
        value={age}
        placeholder="λμ΄λ₯Ό μλ ₯ν΄μ£ΌμΈμ"
        // μΈν μ΄λ²€νΈλ‘ λ€μ΄μ¨ μλ ₯ κ°μ ageμ κ°μΌλ‘ μλ°μ΄νΈ
        onChange={(e) => setAge(e.target.value)}
      />
      ππ<CustomButton color="green" onClick={addUserHandler}>μΆκ°νκΈ°</CustomButton>
    </div>
  );
};

export default App;
```

# **π·`π'key={...}'_ κ° μ€μν μ΄μ `**

> 'key={...}' κ°μ λ£μ§ μμΌλ©΄ κ°λ°μλκ΅¬μμ
> "Each child in a list should have a unique "key" prop."
> (λͺ¨λ  childλ uniqueν keyκ°μ propsλ‘ κ°μ ΈμΌλλ€.) λΌλ μλ¬κ° λ¬λ€.
> κ·Έλμ Reactμμλ mapμ μ¬μ©ν΄μ Componentλ₯Ό λ°λ³΅λ λλ§ν  λ, λ°λμ Componentμ keyλ₯Ό λ£μ΄μ£Όμ΄μΌ νλ€.
> => **Reactμμ Componentλ°°μ΄μ λ λλ§ν  λ κ°κ°μ μμμμ λ³λμ΄ μλμ§ >μμλ΄λ €κ³  μ¬μ©νκΈ° λλ¬Έβ**

> **λ§μ½ `keyκ° μλ€`λ©΄?**
> μμ λ§ν μ€λ₯κ° λ¨λ©°, Reactλ κ°μDomμ λΉκ΅νλ κ³Όμ μμ λ°°μ΄μ μμ°¨μ μΌλ‘ λΉκ΅νλ©΄μ λ³νλ₯Ό κ°μ§νλ €κ³  νλ€. νμ§λ§ keyκ° μμΌλ©΄ μ΄λ€ λ³νκ° μΌμ΄λ¬λμ§, λ λΉ λ₯΄κ² μμλΌ μ μλ€. μ¦ **keyκ°μ λ£μ΄μ£Όμ΄μΌ Reactμ μ±λ₯μ΄ μ΅μ νκ° λλ€.**

---

π²Q1. ageκ° 25μ΄ μ΄μμΈ userλ μ μΈνκ³  λ λλ§νκΈ°
: ageκ° 25λ―Έλ―ΌμΈ userλ νλ©΄μ λ λλ§ν΄μ£Όκ³ , κ·Έκ²μ΄ μλ λλ μλ¬΄κ²λ λ λλ§νμ§ μμΌλ©΄ λ¨. "nullμ return νλ©΄ λ¨β"
null : κ°μ΄ μλ€κ³  νλ κ²μ κ°λ°μκ° μλμ μΌλ‘ νννκ³ μ νλ λ°μ΄ν° ννμ΄μ κ°

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

## πΉμ»΄ν¬λνΈ λΆλ¦¬νκΈ°

### πΉπApp Componentμ User Component, Button Componentκ° λͺ¨λ App.jsνμΌ ν κ³³μ μμ± λμ΄ μκΈ° λλ¬Έμ λ°μνλ λ¬Έμ λ€

`μ²«λ²μ§Έ`, App.jsνμΌμ μ­ν μ΄ λͺννμ§ μλ€.
`λλ²μ§Έ`, Component λΆλ¦¬λ₯Ό ν΅ν΄μ κ°λμ±μ λμμ§λ§ λ Componentμ μ¬μ΄μ¦κ° μ»€μ§κ±°λ λ λ€λ₯Έ Componentλ₯Ό μμ±νκ² λλ©΄ κ°λμ±μ κΈλ°© λ¨μ΄μ§λ€.
`μΈλ²μ§Έ`, νμ¬ κ΅¬μ‘°μμ User Componentμ Button Componentκ° μ΄λμ μμ±λμ΄μλμ§ μ°ΎκΈ°κ° νλ€λ€. νΉν μμ±μκ° μλ λ€λ₯Έ κ°λ°μκ° App.jsνμΌμ λ³΄κ³  User Componentμ Button Componentκ° μ¬κΈ° μμκ±°λΌ μ μΆνκΈ° μ΄λ ΅λ€.
==> **'κ·Έλμ μΌλ°μ μΌλ‘ κ³μ μ¬λ¬λ² λ λλ§ν΄μ κΈ°λ₯μ μ¬μ¬μ©νλ Componentλ€μ λ°λ‘ λΆλ¦¬ν΄μ μ¬μ©νλ€.'**

π μ°Έκ³  : νλμ ν΄λ μμ λͺ¨λ  Componentλ₯Ό λ§λ€μ΄μ κ΄λ¦¬νλ©΄ μκ°μ΄ νλ₯Όμλ‘ Componentκ° λ§μμ Έμ μνλ Componentλ₯Ό μ°ΎκΈ°κ° μ΄λ ΅λ€.
**μ°κ΄λ ComponentλΌλ¦¬ ν΄λλ₯Ό λ§λ€μ΄μ κ΄λ¦¬νλ κ²μ΄ Componentλ₯Ό μ°ΎκΈ°μ μμνλ€.**

### πΉComponent λΆλ¦¬νκΈ°

1. VSCode μΌμͺ½ ν΄λΉ ν΄λ src λ°μ μν΄λλ‘ components ν΄λλ₯Ό λ§λ λ€.
2. components ν΄λμμ CustomButton.jsνμΌμ λ§λ€μ΄μ€λ€.
3. μμ±ν App.jsμμ CustomButton λΆλΆμ μλΌμ κ°μ Έμ¨λ€.
4. **CustomButtonλ₯Ό λΆλ¦¬ν  κ²½μ° μΈλΆμμ μ°κΈ° μν΄** CustomButton μ½λ λ°μ
   **export default CustomButton** μ½λλ₯Ό μΆκ° ν μ μ₯νλ€.
5. App.jsλ‘ λμκ°μ λ΄λ³΄λλ CustomButton μ»΄ν¬λνΈλ₯Ό μ¬μ©νκΈ° μν΄
   **import CustomButton from "./components/CustomButton"**; λ₯Ό μΆκ°νλ€.
   '.' μ  1κ°λ μ΄ μμΉμμ μλκ²½λ‘λ‘ μ΄λμ μλ€. λ λ»μ΄κ³ 
   "./components/CustomButton"λ App.jsμμ μ§κΈ CustomButtonμΈ κ°μ Έμ€κ² λ€λ λ».
