# 🌟 Learned #21

# 🔶캐시(Cache)

## 1. 캐시(Cache)의 장단점과 활용부분

### (1) 캐시(Cache)의 장점

- 캐시에 **데이터를 미리 복사해 놓으면**, 계산이나 접근 시간 없이 **더 빠른 속도로 데이터에 접근 할 수 있습니다.**

### (2) 캐시(Cache)의 단점

- 캐시는 **메모리 저장공간은 속도가 빠를수록 용량이 작고, 가격이 높습니다.**

### (3) 활용부분

- **접근 시간에 비해 원래 데이터에 접근하는 시간이 오래 걸리는 경우** 혹은 값을 다시 계산하는 시간을 절약하고자 하는 경우
- 반복적으로 동일한 결과를 돌려주는 경우(이미지나 썸네일 등)

## 2. 프론트엔드에서 캐시를 사용할 수 있는 2~3가지 영역

### (1) 브라우저 캐싱

- 이전에 방문했던 페이지, 제목의 썸네일 등을 서버로 요청하지 않고, 브라우저에 캐싱을 해두면 사용자는 자신의 요청을 서버로부터 기다리지 않고, 바로 캐시메모리로 응답 받을 수 있어 웹 서핑이 빠르다고 느끼고, 서버는 불필요한 요청을 받지않아 과부하를 피할수 있다.

### (2) proxy

웹 브라우저와 서버 사이에 proxy 라는 것을 두는 방식이다. proxy는 “대리인” 이라는 뜻의 영어 단어로서, 중간에서 뭔가를 대신해주는 것을 '프록시'라고 한다.
프록시의 경우 여러 컴퓨터로부터 요청을 받고 처리하다 보니 같은 데이터가 자주 접근될 확률이 높아져서 캐시의 성능이 좋아지고, 데이터를 캐시에서 반환하는 확률이 더 높아진다.

---

💟 참고자료
<br>
[![캐시 장단점](https://img.shields.io/badge/캐시 장단점-E8E8E8.svg?style=for-the-badge&logo=캐시 장단점&logoColor=white)](https://yanacoding.tistory.com/entry/CS-%EC%BA%90%EC%8B%9CCache%EB%9E%80)
<br>
[![캐시 사용 영역](https://img.shields.io/badge/캐시 사용 영역-E8E8E8.svg?style=for-the-badge&logo=캐시 사용 영역&logoColor=white)](https://hpotter1993.tistory.com/14)
<br>
[![캐시 활용](https://img.shields.io/badge/캐시 활용-E8E8E8.svg?style=for-the-badge&logo=캐시 활용&logoColor=white)](https://mangkyu.tistory.com/69)
<br>
[![캐시 영역](https://img.shields.io/badge/캐시 영역-E8E8E8.svg?style=for-the-badge&logo=캐시 영역&logoColor=white)](https://hpotter1993.tistory.com/14)
