# 🌟 Learned #34

## 🔶 RESTful API 가 아닌 것들

> `RESTful API`?
> 많은 API 개발자들은 RESTful한 API란, ‘각 구성요소들의 역할이 완벽하게 분리되어 있는 것’ 이라고 말합니다.

### **1. 슬래시(/)를 통한 계층 관계 표시**

예를 들어 http://www.homepage.com/users/newuser이라는 URI가 존재한다고 하겠습니다. 여기서 http://www.homepage.com이라는 호스트와 users는 계층관계 입니다. 더 나아가 users와 newuser 또한 계층 관계 입니다. 이러한 계층 관계는 슬래시(/)를 통해 표현됩니다.

그리고 계층의 마지막은 항상 엘리먼트(요소, 리소스) 가 되어야 합니다. 즉 **URI의 마지막은 /(슬래시)로 끝나서는 안됩니다.**

> `Non-Restful API` 첫 번째 : URI의 마지막이 /(슬래시)로 끝나는 경우

### 2. 가독성

URI에서는 계층 관계를 표현할 때, 약속된 문구(단어 형태)를 사용하도록 권장합니다. 여러 리소스들의 집합을 의미하는 컬렉션(리소스 ∈ 컬렉션)의 경우 복수형태(-s) 사용을 권장하고 있으며, 각 리소스(엘리먼트: element)들은 단수를 사용 합니다.

**가장 중요한 부분은 동사가 아닌 ‘명사’로 컬렉션과 엘리먼트를 표현 해야 합니다.**
특히 Under Score(\_)를 사용하는 행위는 꼭 자제해야 합니다. 특정 폰트나 문자에서 명확하지 않은 가독성을 보일 수 있기 때문이죠.

또한 URI는 호스트를 제외한 나머지 모든 요소에서 소문자를 사용 하는 것을 권장합니다. URI는 RFC3986을 기점으로 대소문자가 구별되어 인식되도록 제정되었기 때문이죠. 그러므로 명확한 정의를 위해서 소문자로 통일하여 이름을 짓는 것이 좋습니다. (Users ≠ users)

> `Non-Restful API` 두 번째 : 가독성이 떨어지는 경우

### 3. 파일 확장자는 URI에 미포함

http://www.homepage.com/images/main.jpg 라는 URI가 있습니다. main이라는 이름을 가진 jpg 파일이 있음을 의미하고 있는데, jpg의 경우에는 국제적으로 매우 일반화 된 확장자이기 때문에 큰 문제가 되지 않겠죠?

하지만 확장자가 alz, hwp 등과 같다면 어떻게 할까요? 외국 유저들 중 대다수는 “What the..?” 하는 상황이 올 수도 있겠죠? 이러한 **여러가지 경우의 예외를 두지 않기 위해서 확장자를 포함하지 않는 것으로 규칙을 정했다고 합니다.**

> `Non-Restful API` 세 번째 : 파일확장자(alz, hwp 등)가 URI에 포함된 경우

### 4. 명사 위주의 URI

위에서 가독성 부분에 언급했지만, 조금 더 자세히 알아보겠습니다.

GET http://www.homepage.com/users/delete-olduser 이라는 메소드가 있습니다. GET을 사용했다는 것은 users 컬렉션으로부터 delete-olduser라는 리소스를 반환하고 싶다는 의미인데.. 전체적인 맥락을 보면 delete-olduser가 리소스인지, 오래된 사용자를 제거하겠다는 말인지 혼란을 줄 수 있습니다. 의미만 보면요.

**이처럼 "URI에 동사를 사용하게 되면", 이를 잘못 해석할 수도 있게 됩니다.**
REST API의 경우 정해진 표준이 없기 때문에 다양한 부분에서 혼란이 발생할 여지가 존재하는데요. 이에 많은 부분에서 서로 혼선을 주지 않기 위한 다양한 약속들 중 ‘URI의 명사화’ 또한 하나라고 보시면 좋습니다.

> `Non-Restful API` 네 번째 : URI에 동사를 사용한 경우

---

💟 참고자료
<br>
[![Restful_API](https://img.shields.io/badge/Restful_API-E8E8E8.svg?style=for-the-badge&logo=Restful_API&logoColor=white)](https://aws.amazon.com/ko/what-is/restful-api/)
<br>
[![Non-RestFul_API](https://img.shields.io/badge/Non-RestFul_API-E8E8E8.svg?style=for-the-badge&logo=Non-RestFul_API&logoColor=white)](https://wallees.wordpress.com/2018/04/19/rest-api-restful/)
