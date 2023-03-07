# 🌟 Learned #33

## 🔶 스택(Stack)과 큐(Queue)

### - 스택(Stack) 이란 ?

![](https://velog.velcdn.com/images/wjddms0501/post/5827b80e-12e0-477b-9d03-f1056014ac1b/image.png)

`스택(Stack)`은 "쌓다"라는 의미, **데이터를 차곡차곡 올린 형태의 자료구조**입니다. 위의 사진 대로 데이터가 순서대로 쌓이며 **가장 마지막에 삽입된 자료가 가장 먼저 삭제되는 구조**를 가지고 있습니다.

스택은 정해진 방향대로만 쌓을 수 있으며, **top으로 정한 곳을 통해서만 접근 가능**합니다. 새로 삽입되는 자료는 top이 가르키는 가장 맨 위에 쌓이게 되며, **삭제할 때도 top을 통해서 삭제가 가능**합니다.

스택에서는 삽입 연산을 **'push'**, 삭제 연산을 **'pop'** 라고 하며, 이러한 스택의 구조를 **후입선출**의 구조라고 하고 줄여서 **LIFO(Last In First Out)**이라고 부릅니다.

### 스택(Stack)의 사용 사례

- 웹 브라우저 방문기록 (뒤로가기)
- 실행 취소(undo)
- 역순 문자열 만들기
- 후위 표기법 계산

---

### - 큐(Queue) 란 ?

![](https://velog.velcdn.com/images/wjddms0501/post/1d3fd3b3-5f32-4534-b129-f0d9b06d1176/image.png)

`큐(Queue)`는 스택과 다르게 먼저 들어온 것이 먼저 나가는 **"선입선출"** 구조로, **FIFO(First In First Out)** 의 구조를 가지고 있습니다.

삭제 연산이 수행되는 곳을 프론트(Front), 삽입 연산이 이루어지는 곳은 리어(Rear)로, FIFO 구조를 위해서 스택과 다르게 큐의 한쪽 끝에는 삽입 작업이, 다른 한쪽 끝에서는 삭제 작업이 나뉘어서 이루어지고 있습니다.

큐는 리어(Rear)에서 이루어지는 삽입 연산을 **인큐(Enqueue)** 라고 부르며, 프론트(Front)에서 이루어지는 삭제 연산을 **디큐(Dequeue)** 라고 부릅니다.

### 큐(Queue)의 사용 사례

- 은행업무
- 대기열 순서와 같은 우선순위의 작업 예약 등
- 서비스 센터의 대기시간
- 프로세스 관리

---

💟참고자료
<br>
[![스택/큐](https://img.shields.io/badge/스택/큐-E8E8E8.svg?style=for-the-badge&logo=스택/큐&logoColor=white)](<[링크](https://jud00.tistory.com/entry/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EC%8A%A4%ED%83%9DStack%EA%B3%BC-%ED%81%90Queue%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90#%F-%-F%--%-C%--%EC%-A%A-%ED%--%-D-Stack-%EC%-D%B-%EB%-E%--%--%EB%AC%B-%EC%--%--%EC%-D%BC%EA%B-%-C%-F%C-%A-)>)
