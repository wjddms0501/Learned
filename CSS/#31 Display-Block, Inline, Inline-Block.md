# π Learned #31

## πΆ π¨ Inline μμ & Block μμμ μ°¨μ΄μ 

display μμ±μ κ°μ₯ μ€μν CSS μμ± μ€ νλλ‘, μμλ₯Ό μ΄λ»κ² λ°°μΉν μ§λ₯Ό κ²°μ νλ€.

λͺ¨λ  μμλ κΈ°λ³Έ display μμ±μ κ°μ§λλ° κ·Έ μ€ λνμ μΈ κ°μ΄ block κ³Ό inline μ΄λ€. μ΄ λ μμ±μ νΉμ§μ λμμ κ°μ§λ inline-block μμ±λ μλλ°, μ΄λ κ² 3κ°μ§ μμ±μ΄ CSSμμ κ°μ₯ λ§μ΄ μ¬μ©λλ€. μ΄ ν¬μ€νμμλ block, inline, inline-blockμ λν΄μ μ λ¦¬νλ€.

display μμ± β block, inline νΉμ§ λ° μ°¨μ΄μ 
μλ κ·Έλ¦Όμ λ³΄λ©΄ λ μμ±μ μ°¨μ΄μ μ λν΄μ μ½κ² μ΄ν΄ν  μ μλ€.

## λΈλ‘ μμ (block elements)

![image](https://user-images.githubusercontent.com/118269129/222784996-3aa78263-b644-4ae2-adf3-ca2216b22f62.png)

## μΈλΌμΈ μμ (inline elements)

![image](https://user-images.githubusercontent.com/118269129/222785116-647599ce-3f27-476b-999c-ae24025112c4.png)

---

μ½λ μμ  β BLOCK μμ± VS INLINE μμ±
display μμ±μ λ°λΌ μμκ° μ΄λ»κ² λ°°μΉλλμ§ νμΈνκΈ° μν΄ μμμ λ°°κ²½μμ μμΉ ν΄λ³΄μλ€.

**HTML β inline μμ± νμΈ (span νκ·Έ)**

```
<div>
spanμ <span class="colored"> inline μμ </span> μλλ€. inline μμμ νΉμ±μ λνλ΄κΈ° μν΄ μμ λ°°κ²½μ μμΉ νμ΅λλ€.
</div>
```

**HTML β block μμ± νμΈ (p νκ·Έ)**

```
<div>
pλ <p class="colored"> block μμ γγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγγ</p>μλλ€. block μμμ νΉμ±μ λνλ΄κΈ° μν΄ μμ λ°°κ²½μ μμΉ νμ΅λλ€.
</div>

```

**CSS**

```
.colored{
  background-color: pink;
}
```

**κ²°κ³Ό**

![image](https://user-images.githubusercontent.com/118269129/222785280-2083afac-aeef-4b2c-a538-80f7b24d6b5d.png)
span νκ·Έλ μ€ λ°κΏ μμ΄ λ°°μΉλλ©° λ΄λΆ νμ€νΈ μ¬μ΄μ¦λ§νΌμ λλΉλ₯Ό μ°¨μ§νλ€. λ°λ©΄ block μμ±μΈ p νκ·Έλ μλ‘μ΄ μ€μ λ°°μΉλμκ³  ν μ€λ§νΌμ λλΉλ₯Ό μ°¨μ§νλ€.

---

## BLOCK VS INLINE μ°¨μ΄μ 

![](https://velog.velcdn.com/images/wjddms0501/post/d5dbbac7-3f3f-45be-818a-de67d61f9dfc/image.png)

---

## inline-block

**`inline-block`** μμ±μ **inlineκ³Ό block μμ±μ νΉμ§μ ν¨κ» κ°λλ€.**

- μ€ λ°κΏ μμ΄ ν μ€μ λ€λ₯Έ μμλ€κ³Ό λ°°μΉ κ°λ₯ (inline μμ±)
- width, height, margin-top, margin-bottom μ€μ  κ°λ₯ (block μμ±)

div, p λ± block μμλ₯Ό ν μ€μ μ¬λ¬ κ° λ°°μΉνκ³  μΆμ λ μμ£Ό μ¬μ©λλ€.

**μ½λ μμ . INLINE-BLOCK μμ± μ¬μ©νμ¬ DIVλ₯Ό ν μ€μ λ°°μΉνκΈ°**

<p style="font-size:25px;
		  font-weight:bold;">π[display: inline-block μ μ© μ ]</p>

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

μ μ© μ  λͺ¨μ΅

![image](https://user-images.githubusercontent.com/118269129/222785389-099f2cce-80ce-46c7-b0da-f210b5c420ac.png)
<br>

<p style="font-size:25px;
		  font-weight:bold;">π[display: inline-block μ μ© ν]</p>

```
<div style="border: solid 1px gray;
  			padding: 10px;
            background-color:#dff9fb">
<div style="display:inline-block; /* inline-block μμ±μ μ μ©ν΄ ν μ€μ λ°°μΉ*/
            width: 80px;
            height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 1 </div>
<div style="display:inline-block; /* inline-block μμ±μ μ μ©ν΄ ν μ€μ λ°°μΉ*/
            width: 80px;
            height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 2 </div>
<div style="display:inline-block; /* inline-block μμ±μ μ μ©ν΄ ν μ€μ λ°°μΉ*/
            width: 80px;
            height: 80px;
            border: solid 1px gray;
            background-color: pink;"> children div 3 </div>
</div>
```

μ μ© ν λͺ¨μ΅

![image](https://user-images.githubusercontent.com/118269129/222785475-f01ebc62-f9ec-4eb7-898c-c3770d04fa86.png)

---

π μ°Έκ³ μλ£
<br>
[![inline/block](https://img.shields.io/badge/inline/block-E8E8E8.svg?style=for-the-badge&logo=inline/block&logoColor=white)](https://jinnynote.com/learn/web/display-block-vs-inline/)
