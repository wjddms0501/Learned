# 🌟 Learned #12

# 🔶 Map() 메소드

> `map()` ><br>
> map() 메서드는 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환합니다.

```
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
👇1-14 반복되는 컴포넌트 처리하기

import React from "react";
import "./App.css";

const App = () => {
  const vegetables = ["감자","고구마","오이","가지","옥수수","토마토"]
  return (
    <div className="app-style">
      //👇여기부터
      {vegetables.map((vegetableName) =>{
        return(
          <div className="square-style" key={vegetableName}>
            {vegetableName}
          </div>
        )
      })}
      //👆여기까지<div className="square-style">감자</div>~토마토까지 map()으로 생략해서 나타냄
    </div>
  );
};

export default App;
```

map()은 배열이 가지고 있는 각각의 요소에 함수를 적용시켜주고 그 결과를 반환해주는 메소드. map()은 배열의 모든 요소를 순회한다.

map()을 사용하니까 중복된 코드가 사라지고 한개의 Component 코드를 이용하면서 그 안에서 div vegetablesName이 순차적으로 보여진다.
이처럼

```
'<div className="square-style">감자</div>~토마토'
```

같은 코드가 중복되지 않는데도 각각의 요소들이 div태그가 완성돼서 순차적으로 보여지게 된다.
