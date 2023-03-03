# 🌟 Learned #30

## 🔶 'li'요소와 'ul'요소

li 요소는 목록 아이템을 보여주기 위한 요소이다. 그래서 목록을 담는 ul 요소의 자식 요소여야 한다. 화면 상으로는 아무런 문제가 없더라도 이렇게 li 요소와 ul 요소의 의미에 맞게, 시멘틱하게 HTML을 작성하는 것이 중요하다.

### List, 목록 태그

1. **' ol '태그**

   - 순서가 있는 목록
   - Ordered List

2. **' ul '태그**

   - 순서가 없는 목록
   - Unordered List

3. **' dl '태그**

   - 정의 목록(용어 목록)
   - Definition List

4. **' li '태그**
   - 목록의 항목
   - List Item

---

<span style="background-color:lightyellow">**' ol '태그**</span>

예제 코드

```
<h1>오늘의 할일</h1>

<ol type="i">
    <!-- 여기 안에는 li밖에 못온다. -->
    <li><b>마트</b>에서 장보기</li>
    <li>HTML 정리하기
        <ol>
            <li>태그정리하기</li>
            <li>속성정리하기</li>
        </ol>
    </li>
    <li>강아지 밥주기</li>
    <li>이클립스 설치하기</li>
</ol>
```

**결과 출력**
![](https://velog.velcdn.com/images/wjddms0501/post/35b15559-5b55-47f2-8fde-b09854a4d005/image.png)

<span style="background-color:lightyellow">**' ul ' 태그**</span>

예제 코드

```
<h1>내 일의 할일</h1>

<!-- bullet : 불릿 -->
<ul type="square">
    <li>팀회식</li>
    <li>사우나가기</li>
    <li>오라클 설치하기</li>
    <li>고양이 밥주기</li>
</ul>
```

**결과 출력**
![](https://velog.velcdn.com/images/wjddms0501/post/dc1fed28-9d41-4011-8db6-f5debf4e20f3/image.png)

<span style="background-color:lightyellow">**' dl ' 태그**</span>

예제 코드

```
<h1>자바 용어</h1>
<dl>
    <dt>클래스</dt><!-- definition term. 용어 -->
    <dd>클래스는 이러이러하고 저러저러하다.클래스는 이러이러하고 저러저러하다.</dd><!-- definition description. 용어 설명 -->

    <dt>오라클</dt>
    <dd>클래스는 이러이러하고 저러저러하다.클래스는 이러이러하고 저러저러하다.</dd><!-- definition description. 용어 설명 -->

    <dt>HTML</dt>
    <dd>클래스는 이러이러하고 저러저러하다.클래스는 이러이러하고 저러저러하다.</dd><!-- definition description. 용어 설명 -->
</dl>
```

**결과 출력**
![](https://velog.velcdn.com/images/wjddms0501/post/701f6562-baf8-48fe-9604-560e3c88ed6a/image.png)

---

💟 참고자료
<br>
[![li/ul](https://img.shields.io/badge/li/ul-E8E8E8.svg?style=for-the-badge&logo=li/ul&logoColor=white)](https://velog.io/@line_jeong32/Section-1-%ED%9A%8C%EA%B3%A0)
<br>
[![li/ul/ol/dl_예시](https://img.shields.io/badge/li/ul/ol/dl_예시-E8E8E8.svg?style=for-the-badge&logo=li/ul/ol/dl_예시&logoColor=white)](https://sas-study.tistory.com/118)
