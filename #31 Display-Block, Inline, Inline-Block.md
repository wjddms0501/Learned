# 🌟 Learned #31

## 🔶 🎨 Inline 요소 & Block 요소의 차이점

display 속성은 가장 중요한 CSS 속성 중 하나로, 요소를 어떻게 배치할지를 결정한다.

모든 요소는 기본 display 속성을 가지는데 그 중 대표적인 값이 block 과 inline 이다. 이 두 속성의 특징을 동시에 가지는 inline-block 속성도 있는데, 이렇게 3가지 속성이 CSS에서 가장 많이 사용된다. 이 포스팅에서는 block, inline, inline-block에 대해서 정리한다.

display 속성 – block, inline 특징 및 차이점
아래 그림을 보면 두 속성의 차이점에 대해서 쉽게 이해할 수 있다.

## 블록 요소 (block elements)

<p style="background-color:pink">block</p>
<p style="background-color:yellow">block</p>
<p style="background-color:orange">block</p>
<p style="background-color:yellowgreen">block</p>

## 인라인 요소 (inline elements)

<span style="background-color:pink">block</span><span style="background-color:yellow">block</span><span style="background-color:orange">block</span><span style="background-color:yellowgreen">block</span>

---

코드 예제 – BLOCK 속성 VS INLINE 속성
display 속성에 따라 요소가 어떻게 배치되는지 확인하기 위해 요소의 배경색을 색칠해보았다.

**HTML – inline 속성 확인 (span 태그)**

```
<div>
span은 <span class="colored"> inline 요소 </span> 입니다. inline 요소의 특성을 나타내기 위해 요소 배경을 색칠했습니다.
</div>
```

**HTML – block 속성 확인 (p 태그)**

```
<div>
p는 <p class="colored"> block 요소 　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　</p>입니다. block 요소의 특성을 나타내기 위해 요소 배경을 색칠했습니다.
</div>

```

**CSS**

```
.colored{
  background-color: pink;
}
```

**결과**

<div style="background-color:#dff9fb">
span은 <span style="background-color:pink"> inline 요소 </span>입니다. inline 요소의 특성을 나타내기 위해 요소 배경을 색칠했습니다.
p는
<p style="background-color:pink">block 요소</p>입니다. block 요소의 특성을 나타내기 위해 요소 배경을 색칠했습니다.  
</div>
span 태그는 줄 바꿈 없이 배치되며 내부 텍스트 사이즈만큼의 너비를 차지한다. 반면 block 속성인 p 태그는 새로운 줄에 배치되었고 한 줄만큼의 너비를 차지한다.

---

## BLOCK VS INLINE 차이점

![](https://velog.velcdn.com/images/wjddms0501/post/d5dbbac7-3f3f-45be-818a-de67d61f9dfc/image.png)

---

## inline-block

**`inline-block`** 속성은 **inline과 block 속성의 특징을 함께 갖는다.**

- 줄 바꿈 없이 한 줄에 다른 요소들과 배치 가능 (inline 속성)
- width, height, margin-top, margin-bottom 설정 가능 (block 속성)

div, p 등 block 요소를 한 줄에 여러 개 배치하고 싶을 때 자주 사용된다.

**코드 예제. INLINE-BLOCK 속성 사용하여 DIV를 한 줄에 배치하기**

<p style="font-size:25px;
		  font-weight:bold;">📌[display: inline-block 적용 전]</p>

```
<div style="border: solid 1px gray;
  			padding: 10px;
            background-color:#dff9fb">
<div style="width: 80px;
  			height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 1 </div>
<div style="width: 80px;
  			height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 2 </div>
<div style="width: 80px;
  			height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 3 </div>
</div>
```

적용 전 모습

<div style="border: solid 1px gray;
  			padding: 10px;
            background-color:#dff9fb">
<div style="width: 80px;
  			height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 1 </div>
<div style="width: 80px;
  			height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 2 </div>
<div style="width: 80px;
  			height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 3 </div>
</div>
<br>

<p style="font-size:25px;
		  font-weight:bold;">📌[display: inline-block 적용 후]</p>

```
<div style="border: solid 1px gray;
  			padding: 10px;
            background-color:#dff9fb">
<div style="display:inline-block; /* inline-block 속성을 적용해 한 줄에 배치*/
            width: 80px;
            height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 1 </div>
<div style="display:inline-block; /* inline-block 속성을 적용해 한 줄에 배치*/
            width: 80px;
            height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 2 </div>
<div style="display:inline-block; /* inline-block 속성을 적용해 한 줄에 배치*/
            width: 80px;
            height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 3 </div>
</div>
```

적용 후 모습

<div style="border: solid 1px gray;
  			padding: 10px;
            background-color:#dff9fb">
<div style="display:inline-block;
  width: 80px;
  height: 80px;
  border: solid 1px gray;
  background-color: pink;"> children div 1 </div>
<div style="display:inline-block;
  width: 80px;
  height: 80px;
  border: solid 1px gray;
  background-color: pink;"> children div 2 </div>
<div style="display:inline-block;
  width: 80px;
  height: 80px;
  border: solid 1px gray;
  background-color: pink;"> children div 3 </div>
</div>

---

💟 참고자료
<br>
[![inline/block](https://img.shields.io/badge/inline/block-E8E8E8.svg?style=for-the-badge&logo=inline/block&logoColor=white)](https://jinnynote.com/learn/web/display-block-vs-inline/)
