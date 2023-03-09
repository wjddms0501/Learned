# 🌟 Learned #36

## 🔶 TCP 와 UDP

### TCP(Transmission Control Protocol)

TCP는 신뢰성 있는 데이터 전송을 지원하는 연결 지향형 프로토콜입니다.

일반적으로 TCP와 IP가 함께 사용되는데, IP가 데이터의 전송을 처리한다면 TCP는 패킷 추적 및 관리를 하게 됩니다. 연결 지향형인 TCP는 3-way handshaking이라는 과정을 통해 연결 후 통신을 시작하는데, 흐름 제어와 혼잡 제어를 지원하며 데이터의 순서를 보장합니다.

### TCP 특징

- 연결형 서비스로 가상 회선 방식을 제공
- 데이터의 전송 순서 보장
- 데이터의 경계를 구분하지 않음
- 신뢰성 있는 데이터 전송
- UDP보다 전송속도가 느림
- 연결을 설정(3-way handshaking)과 해제(4-way handshaking)

### UDP (User Datagram Protocol)

UDP는 비연결형 프로토콜로써, 인터넷상에서 서로 정보를 주고받을 때 정보를 보낸다는 신호나 받는다는 신호 절차를 거치지 않고 보내는 쪽에서 일방적으로 데이터를 전달하는 통신 프로토콜입니다.

TCP와는 다르게 연결 설정이 없으며, 혼잡 제어를 하지 않기 때문에 TCP보다 전송 속도가 빠릅니다. 그러나 데이터 전송에 대한 보장을 하지 않기 때문에 패킷 손실이 발생할 수 있습니다.

### UDP 특징

- 비연결형 서비스로 데이터그램 방식을 제공
- 비신뢰성
- 데이터의 경계를 구분
- 패킷 오버해드가 적어 네트워크 부하 감소
- 혼잡 제어를 하지 않기 때문에 TCP보다 빠름
- TCP의 handshaking 같은 연결 설정이 없음

### TCP vs UDP

![](https://velog.velcdn.com/images/wjddms0501/post/9b688a72-d36a-487e-8326-d07adb28473a/image.png)

### TCP와 UDP요약

TCP는 연속성보다 신뢰성 있는 전송이 중요할 때에 사용되는 프로토콜이며,
UDP는 TCP보다 빠르고 네트워크 부하가 적다는 장점이 있지만 신뢰성 있는 데이터 전송을 보장하지는 않습니다.
그렇기 때문에 신뢰성보다는 연속성이 중요한 실시간 스트리밍과 같은 서비스에 자주 사용됩니다.

![](https://velog.velcdn.com/images/wjddms0501/post/392e373c-996b-4447-88b6-63f3353f4294/image.png)

![](https://velog.velcdn.com/images/wjddms0501/post/9ea11f71-36ea-4cc4-b941-36b0c8380351/image.png)

---

💟 참고자료
<br>
[![TCP/UDP_비교_표](https://img.shields.io/badge/TCP/UDP_비교_표-E8E8E8.svg?style=for-the-badge&logo=TCP/UDP_비교_표&logoColor=white)](https://cocoon1787.tistory.com/757)
