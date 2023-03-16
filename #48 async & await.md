# 🌟 Learned #48

## 🔶 async & await

`async`, `await`이란 비동기 처리 패턴 중 가장 최근에 나온 문법입니다.

**async**는 함수 앞에 위치시켜 사용하며 해당 함수는 항상 promise를 반환합니다. promise가 아닌 값을 반환하여도 이행상태의 promise로 감싸 이행된 promise가 반환되도록 합니다.

**await**는 promise가 처리될 때까지 기다립니다. 함수를 호출하고 함수가 실행되는동안 await을 만나면 잠시 중단 되었다가 promise가 처리되면 그다음 실행하게 됩니다. **await는 항상 async 안에서 사용**해야 합니다.

**async/await은 읽고 쓰기 편한 비동기 코드를 작성할 수 있는 장점**이 있습니다.
