# ๐ Learned #8

# ๐ถ<props>

> props
> : ๋ถ๋ชจ Component์์ ๋ด๋ ค์ค๋ ๋ชจ๋  ๋ฐ์ดํฐ
> => ์ฐ๋ฆฌ๊ฐ ๋ด๋ ค์ค ๋ฐ์ดํฐ๋ "Props๊ฐ์ฒด ์์ ์ด๋ ๊ฒ ์กด์ฌํ๋๊ตฌ๋"๋ฅผ ์ ์ ์์.

```
function Mother() {
  const name = "ํ๋ถ์ธ";
  return <Child Mothername={name} />;
  //๐๋ถ๋ชจ์ปดํฌ๋ํธ์์ ์์์ปดํฌ๋ํธ๋ก props๋ฅผ ๋ด๋ ค์ฃผ๋ ๋ฐฉ๋ฒ
}

function Child(props) {
              //๐(props)๋ถ๋ถ์ 'props๋ก ๋ค์์ ์ ๋ฌํ๋ค.'๋ผ๊ณ  ํจ
  console.log(props); //๊ฐ๋ฐ์๋๊ตฌ์์ props๊ฐ ์ ๋๋์ง ์ฝ์์ ์ฐ์ด๋ณด๊ธฐ
  return <div>{props.Mothername}</div>;
    //๐์์์ปดํฌ๋ํธ์์ ๋ฐ์์จ ๋ฐ์ดํฐ์ ์ ๊ทผํด์ ์ฌ์ฉํ๋ ๋ฐฉ๋ฒ
}
```

๊ผญ 'props'๋ผ๊ณ  ์ด๋ฆ์ ์ง์ด์ค์ผํ ๊น?
=> ์ฝ๋์ ๊ฐ๋์ฑ์ ์ํด 'Props'๋ผ๊ณ  ์ด๋ฆ์ ์ฃผ๋ ๊ฒ๋ฟ, ์๋ฏธ์๋ ๋ณ์ ์ด๋ฆ 'aaa'๋ก๋ ๊ฐ๋ฅํ๋ค.

## ๐นProps์ ํน์ฑ ์ค ์์์ผ ํ  ํ๊ฐ์งโ

Props๋ ์ค์ง '๋ถ๋ชจComponent์์ ์์Component๋ฐฉํฅ์ผ๋ก๋ง' Props๋ฅผ ์ ๋ฌ ํ  ์ ์๋ค.

## ๐นprops : ๋ถ๋ชจ Component์์ ๋ด๋ ค์ค๋ ๋ชจ๋  ๋ฐ์ดํฐ

=> ์ฐ๋ฆฌ๊ฐ ๋ด๋ ค์ค ๋ฐ์ดํฐ๋ "Props๊ฐ์ฒด ์์ ์ด๋ ๊ฒ ์กด์ฌํ๋๊ตฌ๋"๋ฅผ ์ ์ ์์.

> Children ?
> Component ์ฌ์ด์ ์ ๋ณด๋ฅผ ์๋ ฅํ๋ ๋ฐฉ์์ผ๋ก ์ ๋ฌ.
> Layout ์ด๋ผ๋ Component ํด์ ๋ง๋ค ๋ ์์ฃผ ์ฌ์ฉํจ.

```
function User(props){
return <div>props.children</div>;
}
//(props)๋ฅผ ํ๊ณ , ๋ฐ์ props.children์ ํด์ฃผ์ด์ผ ๋ฐ ์ฝ๋์์ Userํ๊ทธ๋ฅผ ๋ถ๋ฌ์ฌ ์ ์์.

function App() {
return <User>์๋ํ์ธ์</User>;
}

```

## \* ๊ตฌ์กฐ๋ถํดํ ๋น์ props์ ์ ์ฉํ๋ฉด props์์ ๊ฐ์ ๊ฐ์ ธ์ฌ ๋ ๋ ๊ฐํธํ๋ฉด์ ๊ฐ๋์ฑ์ ๋์ผ ์ ์์.

## ๐น<props์ ํํ>

```
function ๊ฐ์ฒด์ด๋ฆ(props) {
return <div>{props.๊ฐ์ฒด์ด๋ฆ}</div>
}
<์๋ฐ์คํฌ๋ฆฝํธ์ ๊ตฌ์กฐ๋ถํดํ ๋น์ ์ด์ฉํ props์ ํํ>

function ๊ฐ์ฒด({title}) {   //์ค๊ดํธ์์ ๊ฐ์ฒด์ Key name ์ ์ด์ฃผ๊ธฐ
return <div>{title}</div>
}
.
.
//๊ตฌ์กฐ๋ถํดํ ๋น์ ํ์ง ์์๋ค๋ฉด, props.title๋ก ๊ฐ์ ์ ๊ทผํ์ ๊ฒ์
```

Props๋ฅผ ํ์ฉํ  ๋ ์ด Props๋ฅผ ๋ฐ์์ค๋ ๊ฐ์ Default Props๋ผ๋ ๊ฒ์ ์ค์ ํด ์ค ์ ์์.
Props ์ค์๋ ์์ฃผ ๋ฐ๊ฑฐ๋ ๋ฌด์กฐ๊ฑด ๋ฐ์์ผํ๋ Props๋ค์ด ์์
-> ๊ฐ์ด ์์ผ๋ฉด ๋ฌธ์ ๊ฐ ๋๊ฑฐ๋, UX๊ฐ ์ด์ํด์ง๋ ๊ฒฝ์ฐ
ex) ๋ก๊ทธ์ธ์ด ์๋ฃ๋๊ธฐ ์ ๊น์ง ๋ด ์ด๋ฆ์ ๋ฐ์ ์ค์ง ์๋๋ฐ '\_\_\_\_'๋ ์๋ํ์ธ์! < ์ด๋ฐ ๊ฒฝ์ฐ.

## ๐น<Default Props์ ํํ>

```
Child.defaultProps={
name: '๊ธฐ๋ณธ ์ด๋ฆ'
}
<๊ตฌ์กฐ๋ถํดํ ๋น์ ์ด์ฉํด ๊ฐ์ฒด์ ์ง์  ์ ๊ทผํ Default Props์ ํํ>

function Child({name="๊ธฐ๋ณธ์ด๋ฆ"}) {
return <div>๋ด ์ด๋ฆ์ {name} ์๋๋ค. </div>
}
```

๋ถ๋ชจ Component์์ Props๊ฐ ๋ด๋ ค์ค๊ฒ ๋๋ฉด Defualt Porps์ ๊ฐ์ ์ฌ๋ผ์ง๊ณ  ๋ด๋ ค๋ฐ์ props๋ก ๊ฐ์ด ๋์ฒด๋๋ค.

---

๐ ์ฐธ๊ณ ์๋ฃ
<br>
[![Prop Drilling](https://img.shields.io/badge/Prop Drilling-E8E8E8.svg?style=for-the-badge&logo=Prop Drilling&logoColor=white)](https://slog.website/post/13)
<br>
[![PropTypes](https://img.shields.io/badge/PropTypes-E8E8E8.svg?style=for-the-badge&logo=PropTypes&logoColor=white)](https://ko.reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper)
<br>
[![Hook](https://img.shields.io/badge/Hook-E8E8E8.svg?style=for-the-badge&logo=Hook&logoColor=white)](https://ko.reactjs.org/docs/hooks-overview.html)
