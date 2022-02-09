---
layout: post
title: CSS - layout3 (Flexbox)
date: 2022-02-09 14:00:00 +0900
category: CSS
---

Flexbox
===

<br />

> Flexbox 레이아웃

```html
<div class="flex-container">
  <div class="box"></div>
  <div class="box"></div>
  <div class="box"></div>
</div>
```

```css
.flex-container {
  display : flex;
}
.box {
  width : 100px;
  height : 100px;
  background : grey;
  margin : 5px;
}
```

박스들을 감싸는 부모 요소에게 display : flex를 사용하면 됩니다.<br />
기본적으로 가로정렬로 배치됩니다.<br />
익스플로러 11이하는 지원 안됩니다.<br />

<br />

> Flexbox 세부속성

```css
.flex-container {
  display : flex;
  justify-content : center;  /* 좌우정렬 */
  align-items : center;  /* 상하정렬 */
  flex-direction : column; /* 세로정렬 */
  flex-wrap : wrap;  /* 폭이 넘치는 요소 wrap 처리 */
}
.box {
  flex-grow : 2;  /* 폭이 상대적으로 몇배인지 결정 */
}
```

<br />

> 박스 좌측 & 우측 정렬

```html
<div class="flex-container">
  <div class="box"></div>
  <div class="box" style="flex-grow : 1"></div>
  <div class="box"></div>
</div>
```

<br />

> align-content

display : flex; 이걸 준 요소에 align-content 속성을 줄 수 있는데<br />
이러면 내부에 들어있는 박스들의 상하정렬이 어떻게 될지 조절할 수 있습니다.<br />
align-content는 박스가 가로로 여러줄일 때 박스들의 상하배치를 조절할 수 있는 속성입니다.<br />

```css
/* 속성 */
align-content: flex-start,
align-content: flex-end,
align-content: center,
align-content: stretch,
align-content: space-between,
align-content: space-around,
```

<br />
참고 (References)
<br />[codingapple](https://codingapple.com/)
