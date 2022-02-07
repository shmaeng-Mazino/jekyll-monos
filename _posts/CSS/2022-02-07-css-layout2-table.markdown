---
layout: post
title: CSS - layout (table)
date: 2022-02-07 10:00:00 +0900
category: CSS
---

layout (table)
===

<br />

> table HTML 구성 

```html
<table>
  <thead></thead>
  <tbody>
    <tr>
      <td>내용</td>
      <td>내용</td>
    </tr>
  </tbody>
</table>
```

<br />

> 테이블 셀 내에서 상하정렬할 땐 vertical-align 

```css
td, th {
    vertical-align : middle;
}
```

vertical-align 속성을 이용해 테이블 내에서의 상하정렬을 하실 수 있습니다.<br />
top, bottom, middle 사용가능<br />

<br />

> inline 요소 간 상하정렬할 땐 vertical-align

```html
<p>
    <span style="font-size : 50px">Greetings</span> 
    <span style="font-size : 20px; vertical-align : bottom;">안녕</span>
</p>
```

display : inline 혹은 inline-block 요소들을 나란히 배치하면 상하정렬이 이상한 경우가 있습니다.<br />
이런걸 나란히 배치했을 때 서로 높이가 맞지 않는 경우가 많은데<br />
이럴 때 margin-top 이런거 대신 쓰는 속성입니다.<br />
top, middle, bottom 말고도 super, sub, px 단위로 사용가능합니다. <br />
(table 안에선 top, middle, bottom만 사용가능합니다)<br />

<br />
<br />
참고 (References)
<br />[codingapple](https://codingapple.com/)
