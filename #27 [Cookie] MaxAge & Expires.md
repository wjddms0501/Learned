# 🌟 Learned #27

# 🔶브라우저 저장소

## Cookie & MaxAge & Expires

> **`쿠키(Cookie)`** 란?
> 웹 브라우저 상에 작은 ‘텍스트 파일’로 저장이 되는 만료 기간이 존재하는 저장소를 의미합니다.

**`Expires`** : 쿠키가 삭제되는 만료 날짜를 설정합니다.

```
💡 쿠키를 파기하는 속성입니다. 해당 만료일은 UTC 시간을 기준으로 지정합니다.
💡 구조: Expires=<date>

const expired = new Date();
expired.setTime(expired.getTime() + expiresHour * 24 * 60 * 60 * 1000);

// 쿠키 예시
document.cookie = `userId=adjh54; Path=/; Expires=${expired}`;
```

**`Max-Age`** : 쿠키가 삭제될 시간을 초 단위로 설정합니다
쿠키를 따로 설정하지 않았다면 브라우저의 생존주기와 동일하게 가기 때문에 사라지게 됩니다. Max-Age 라는 옵션을 통해 브라우저와는 별개로 쿠키를 외부파일로 저장하는 것이 가능합니다.

```
💡 expries의 대안으로 쿠키의 만료시간을 설정할 수 있게 해주는 속성
💡 구조: Max-Age=<number>

// 쿠키 예시
document.cookie = `userId=adjh54; Path=/; Max-Age=3600`;
```

> expires(유효 일자)나 max-age(만료 기간) 옵션이 **지정되어있지 않으면**, _**브라우저가 닫힐 때 쿠키도 함께 삭제됩니다.**_ 이런 쿠키를 "세션 쿠키(session cookie)"라고 부릅니다.

---

💟 참고자료
<br>
[![MaxAge/Expires_1](https://img.shields.io/badge/MaxAge/Expires_1-E8E8E8.svg?style=for-the-badge&logo=MaxAge/Expires_1&logoColor=white)](https://nyagm.tistory.com/177)
<br>
[![MaxAge/Expires_2](https://img.shields.io/badge/MaxAge/Expires_2-E8E8E8.svg?style=for-the-badge&logo=MaxAge/Expires_2&logoColor=white)](https://studee.tistory.com/55)
