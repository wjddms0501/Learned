# 🌟 Learned #22

# 🔶HTTP

## 1. HTTP?

`HTTP`란 인터넷에서 데이터를 주고받을 수 있는 프로토콜

## 2. HTTP 메세지 구조

HTTP 메시지 타입은 두 가지가 있습니다.
`요청(request)`은 클라이언트가 서버로 전달해서 서버의 액션이 일어나게끔 하는 메시지고 공백을 제외하고 start line, headers, body로 3가지 부분으로 나누어집니다.
`응답(response)`은 요청에 대한 서버의 답변이고 공백을 제외하고 status line, headers, body로 3가지 부분으로 나누어집니다.

## 3. HTTP & HTTPS 차이점

`HTTPS(https://)`는 **SSL(Secure Socket Layer) 인증서를 사용하는 HTTP(http://)** 입니다. **SSL(또는 TLS) 인증서는 일반 HTTP 요청 및 응답을 암호화합니다.**
따라서 **HTTPS는 HTTP보다 더 안전한 보안용 프로토콜이라고 할 수 있습니다**.

HTTP와 HTTPS의 유일한 `차이점`은 **HTTPS를 사용한 웹 페이지를 통해 전송되는 모든 데이터는 추가적인 보안 계층**이 있습니다. 이를 **TLS(전송 계층 보안) 프로토콜**이라고 합니다. **모든 유형의 데이터는 변경되거나 손상될 수 없는 HTTPS 사이트를 통해 전달되며 제3자로부터 보호됩니다.**

---

💟 참고자료
<br>
[![HTTP_메세지_구조](https://img.shields.io/badge/HTTP_메세지_구조-E8E8E8.svg?style=for-the-badge&logo=HTTP_메세지_구조&logoColor=white)](https://hahahoho5915.tistory.com/62)
