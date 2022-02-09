---
layout: post
title: CSS - responsive layout (Flexbox)
date: 2022-02-09 15:00:00 +0900
category: CSS
---

Responsive Design
===

<br />

> 모던 웹에서 사용하는 단위정리

```css
.box {
  width : 16px; /* 기본 px 단위 */
  width : 1.5rem; /* html태그 혹은 기본 폰트사이즈의 1.5배 */
  width : 2em; /* 내 폰트사이즈 혹은 상위요소 폰트사이즈의 2배 */
  width : 50vw; /* 브라우저(viewport) 화면 폭의 50% */
  width : 50vh; /* 브라우저(viewport) 화면 높이의 50% */
}
```

<br />

> responsive head

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

<br />

> media query 

```css
@media screen and (max-width : 1200px) { 
  .box { 
    font-size : 40px; 
  } 
} 

@media screen and (max-width : 768px) { 
  .box { 
    font-size : 30px; 
  } 
}
```

CSS 파일 최하단에 사용합니다.<br />
현재 브라우저의 폭이 1200px 이하일 경우에 안에 있는 class가 중복 적용이 됩니다.<br />
여러개 원하는 만큼 사용가능합니다.<br />
그래서 위의 코드는 브라우저 폭이 1200px 이하면 .box { font-size : 40px } 이걸 적용해주고<br />
768px 이하면 .box { font-size : 30px } 을 적용해줍니다. <br />
<br />
(참고) 적용은 아니고 class를 밑에 하나 더 추가해준다라고 이해하시는게 정확합니다.<br />
그러면 class 안의 font-size 스타일 중복이 발생하는데<br />
중복이 발생하면 원래 더 밑에 있는 스타일을 적용해줍니다. <br />

<br />

> 권장 Breakpoint 

media query 문법 max-width 안에 넣는 브라우저 폭을 breakpoint라고 합니다.<br /> 
breakpoint는 원하는 만큼 저렇게 여러개 넣을 수 있는데 <br />
필요할 때 마다 사이즈를 임의로 넣고 작성하는 것 보다는<br />
많은 사람들이 사용하는 breakpoint를 쓰는게 좋습니다. <br />
<br />
1200px / 992px / 768px / 576px<br />
이런 사이즈를 권장드립니다.<br />
Bootstrap 라이브러리가 기본으로 권장하는 breakpoint 이며 1200px부터를<br />
태블릿사이즈로 볼지, 992px 부터를 태블릿 사이즈로 볼지 또, 768px 부터를<br />
모바일로 볼지, 576px 부터를 모바일로 볼지도 상황에 따라 다릅니다.<br />
<br />
간편하게 1200px, 768px 이렇게 두개만 골라서 1200px 이하는 태블릿,<br />
768px 이하는 모바일 이렇게 디자인하는 방법도 있습니다.<br />
<br />
<br />

참고 (References)
<br />[codingapple](https://codingapple.com/)
