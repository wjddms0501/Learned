# 🌟 Learned #46

## 🔶 변수의 종류(var, let, const)

### 변수의 종류

`var` : 자바스크립트의 기본 변수로 초기에 만들어진 **변수**(원조격)
`let` : 나중에 추가된 변수로 블록 범위 **변수**이다.
`const` : 나중에 추가된 변수로 블록 범위이면서 **상수**이다.

![](https://velog.velcdn.com/images/wjddms0501/post/3d29857a-8b0f-4b97-8fe9-bfaeb48442c6/image.png)

### (1) var

- 자바스크립트의 기본 변수로 초기에 만들어진 변수(원조격)
- 변수의 선언 및 사용 범위는 전역(함수)범위이다.
- var는 함수 내부에 선언된 변수만 지역변수로 한정하며, 나머지는 모두 전역변수로 간주한다.
- 재(중복) 선언 O, 재할당 O

```
<script>
    // 1. 중복 선언
    var va = 10;
    console.log("첫번째 var 변수 선언 및 초기화(10) : " + va); // 10

    var va = 20;
    console.log("두번째 var 변수 선언 및 초기화(20) : " + va); // 20

    var va;
    console.log("세번째 var 변수 선언 및 초기화(X) : " + va); // 20

    var va1;
    console.log("네번째 var 변수 선언 및 초기화(X) : " + va1); // 20

    // 2. 재할당
    var vb = 10;
    vb = 20;
    console.log("var 변수 재할당 : " + vb) // 20
</script>
```

### (2) let

- 나중에 추가된 변수로 블록 범위 변수이다.
- 변수의 선언 및 사용 범위는 로컬범위
- 재(중복) 선언 X, 재할당 O

```
<script>
    // 1. 중복 선언
    let la = 10;
    console.log("첫번째 let 변수 선언 및 초기화(10) : " + la); // 10

    // 중복 선언이 불가능하다.
    // let la = 20;
    // console.log("두번째 let 변수 선언 및 초기화(20) : " + la)

    // 2. 재할당
    let lb = 30;
    lb = 40;
    console.log("let 변수 재할당 : " + lb) // 40
</script>
```

### (3) const

- 나중에 추가된 변수로 블록 범위이면서 상수이다.
- 변수의 선언 및 사용 범위는 로컬(블록) 범위이다.
- 재(중복) 선언 X, 재할당 X ---> 상수
- 즉, 자바스크립트에서 사용하는 상수 선언 방식이다.

```
<script>
    // 1. 중복 선언
    const ca = 10;
    console.log("첫번째 const 변수 선언 및 초기화(10) : " + ca); // 10

    // 중복 선언이 불가능하다.
    // const ca = 20;
    // console.log("두번째 const 변수 선언 및 초기화(20) : " + ca);

    // 2. 재할당
    // const
    const cb = 10;
    // cb = 20;    // 재할당 불가(오류)
    console.log("const 변수 재할당 : " + cb);
</script>
```

### (4) 스코프(Scope)

- 변수에 접근할 수 있는 범위
- 변수의 생명주기
- 변수의 유효 범위
- var는 전역 범위이고 let과 const는 블록( { } ) 범위이다.

```
<script>
    // 스코프 : 전역변수 vs 지역변수
    if(true) {
        var var1 = "123";
        let var2 = "456";
        const var3 = "789";

        console.log(var1);
        // console.log(var2);   // 오류
        // console.log(var3);   // 오류
    }
</script>
```

---

💟 참고자료
<br>
[![var/let/const/scope](https://img.shields.io/badge/var/let/const/scope-E8E8E8.svg?style=for-the-badge&logo=var/let/const/scope&logoColor=white)](https://tadaktadak-it.tistory.com/135)
<br>
[![var/let/const 차이_비교_표](https://img.shields.io/badge/var/let/const 차이*비교*표-E8E8E8.svg?style=for-the-badge&logo=var/let/const 차이*비교*표&logoColor=white)](https://technote.kr/385)
