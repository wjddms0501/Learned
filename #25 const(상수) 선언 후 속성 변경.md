# 🌟 Learned #25

# 🔶브라우저 저장소

## const로 상수 선언→속성 변경?

> **`const` 선언은 블록 범위의 상수를 선언합니다. 상수의 값은 재할당할 수 없으며 다시 선언할 수도 없습니다.**

**const**는 변하지 않는 상수인데 배열과 객체는 요소를 추가/삭제하며 변경을 할 수 있습니다.
그렇다면 const로 배열과 객체를 선언하지 못 하는 것 아닌가요..🤷‍♀️?

### 배열과 객체를 const로 선언했는데 요소나 속성을 추가할 수 있는 이유 ?

> const로 선언한 변수에 객체나 배열 컬렉션을 값으로 할당한다면 객체나 배열 요소에 대하여 자유롭게 값(요소)을 추가 및 삭제할 수 있습니다.

> 이것은 상수가 실제로는 배열에 대한 참조를 저장하기 때문에 발생하는 현상입니다.
> **배열에 무언가를 결합할 때 상수 값을 수정하는 것이 아니라 가리키는 배열을 수정하는 것**입니다. 또한 객체를 상수에 할당하고 그 속성을 수정하려는 경우에도 마찬가지입니다.

**객체의 경우 상수로 선언해도 메모리값만 상수일 뿐 객체 안의 내용은 변경이 가능하다. 즉 객체가 저장된 공간을 가리키는 정보만 상수일뿐 그 객체의 정보 자체는 변경이 가능하다.**
이런 이유로 JavaScript에서 객체는 변수로 선언할 이유가 없으며 거의 모든 케이스에서 상수로 선언하는게 일반적이다.

### 객체 Example

```
const user = { name: '홍진혁' }; // { name: '홍진혁' }
user.name = '홍진호'; // { name: '홍진호' }

delete user.name; // {}

user.name = '홍진혁' // { name: '홍진혁' }
user.job = 'cloud engineer'; // { name: '홍진혁', job: 'cloud engineer }
```

### 배열 Example

```
const arr = [ '홍진혁' ]; // ['홍진혁']
arr.push('홍진호'); // ['홍진혁', '홍진호']
arr.splice(0, 1); // ['홍진호
```

---

💟 참고자료
<br>
[![const재할당1](https://img.shields.io/badge/const재할당1-E8E8E8.svg?style=for-the-badge&logo=const재할당1&logoColor=white)](https://velog.io/@xmun74/const%EB%A1%9C-%EB%B0%B0%EC%97%B4%EA%B0%9D%EC%B2%B4%EB%A5%BC-%EC%84%A0%EC%96%B8%ED%95%98%EC%97%AC-%EC%9A%94%EC%86%8C%EB%A5%BC-%EB%B3%80%EA%B2%BD%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94)
<br>
[![const재할당2](https://img.shields.io/badge/const재할당2-E8E8E8.svg?style=for-the-badge&logo=const재할당2&logoColor=white)](https://velog.io/@ragnarok_code/%EC%83%81%EC%88%98-%EA%B0%9D%EC%B2%B4%EC%99%80-%EB%B0%B0%EC%97%B4%EC%9D%98-%EC%9A%94%EC%86%8C-%EB%B3%80%EA%B2%BD)
