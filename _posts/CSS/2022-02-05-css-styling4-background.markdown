---
layout: post
title: CSS - styling4 (background)
date: 2022-02-05 06:00:00 +0900
category: CSS
---

background
===

<br />

> 배경관련 CSS 속성 

```css
.main-background {
  background-image : url(../img/shoes.jpg);
  background-size : cover;
  background-repeat : no-repeat;
  background-position : center;
  background-attachment : fixed;
}
```

<br />

**background-repeat**<br />
배경 이미지의 반복을 지정한다. 수직, 수평 또는 수직과 수평 모두의 반복을 지정할 수 있다.<br />
repeat, repeat-x, repeat-y, no-repeat<br />
<br />

**background-position**<br />
이미지의 좌표(xpos, ypos)를 지정 할 수 있다.<br />
기본값은 background-position: 0% 0%;로 배경이미지는 우측 상단에 위치하게 된다.<br />
<br />

**background-attachment**<br />
일반적으로 화면을 스크롤하면 배경 이미지도 함께 스크롤된다.<br />
화면이 스크롤되더라도 배경이미지는 스크롤되지 <br />
않고 고정되어 있게 하려면 background-attachment 프로퍼티에 fixed 키워드를 지정한다.<br />
<br />
<br />

참고 (References)
<br />[poiemaweb.com](https://poiemaweb.com/css3-background)
