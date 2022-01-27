---
layout: post
title: CSS (vertical-align)
date: 2021-01-27 22:00:00 +0900
category: css
---

- vertical-align 속성을 실험해볼 이미지와 글자

```html
<div>
    <img src="https://mdn.mozillademos.org/files/12245/frame_image.svg" width="32" height="32"> image with a default alignment.
</div>
```

- 기본적인 table HTML 구성 

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

- 테이블 셀 내에서 상하정렬할 땐 vertical-align 

```css
td, th {
  vertical-align : middle;
}
```

vertical-align 속성을 이용해 테이블 내에서의 상하정렬을 하실 수 있습니다.
top, bottom, middle 사용가능


- inline 요소 간 상하정렬할 땐 vertical-align 

```html
<p>
  <span style="font-size : 50px">Greetings</span>   <span style="font-size : 20px">안녕</span>
</p>
```

display : inline 혹은 inline-block 요소들을 나란히 배치하면 상하정렬이 이상한 경우가 있습니다.
특히 큰 이미지와 글,
또는 큰 글씨옆에 있는 작은 글씨
이런걸 나란히 배치했을 때 서로 높이가 맞지 않는 경우가 많은데
이럴 때 margin-top 이런거 대신 쓰는 속성입니다.
위의 예제에서 `<span>`안녕`</span>` 여기에 vertical-align : top 이런거 넣어서 실험해보십시오. 
top, middle, bottom 말고도 super, sub, px 단위로 사용가능합니다. 
(table 안에선 top, middle, bottom만 사용가능합니다)

- display : table 

```css
.box {
  display : table;
  display : table-row;
  display : table-cell;
}
```

가끔 div로 이루어진 요소들을 테이블화 시키고 싶을 때가 있습니다
그럴 땐 table태그로 변하길 원하는 요소에 display : table을 적어주신 뒤에
tr로 변하길 원하는 요소엔 display : table-row,
td로 변하길 원하는 요소엔 display : table-cell 을 넣어주면 됩니다. 
하지만 그럴 일은 거의 없기 때문에 참고로만 알아둡시다. 

- nth-child 셀렉터 

```html
.cart-table td:nth-child(2) {
  color: red;
} 
```

여러 요소를 찾은 다음
원하는 n번째 요소만 스타일을 주고 싶으면 :nth-child(n) 이걸 뒤에 붙여주면 됩니다.
위의 코드는 그래서 .cart-table 안에 있는 모든 td를 찾은 다음
2번째 나오는 td에만 color를 줄 수 있습니다. 
테이블에서 원하는 순서의 셀에 스타일줄 때 가끔 유용하게 사용합니다.


```css
.cart-table td:nth-child(even) {
  color: red;
} 
```

이러면 짝수로 등장하는 td에만 스타일을 줄 수도 있고
(odd라고 쓰면 홀수입니다)

```css
.cart-table td:nth-child(3n+0) {
  color: red;
} 
```

이러면 3의 배수로 등장하는 3,6,9,12.. 번째 등장하는 요소에만 스타일을 줄 수 있습니다.
3n + 1 이렇게 작성하면 (3의배수 +1) 번째 등장하는 요소에만 스타일을 줄 수 있습니다.


- 포인트1. 테두리 색상은 밑에만 넣고 싶으면

```css
td, th {
  border-bottom : 1px solid black;
}
```

- 포인트2. 셀 블록마다 width를 설정해줄 수 있습니다.

```html
<table>
  <tr>
    <td class="name">상품명</td>
    <td class="price">가격</td>
    <td>수량</td>
  </tr>
</table>
```

```css
.name {
  width : 50%
}
.price {
  width : 20%
}
```

하나의 td에 width를 주어도 전체 열의 width가 변합니다.
나름 편리한 점이라고 볼 수 있겠습니다.

- 포인트3. td 여러개를 합치고 싶으면
colspan에 원하는 숫자를 넣으면 그 숫자만큼 옆의 셀을 합쳐줍니다. 

- table 태그에 border-radius가 안먹을 때 1. 

```css
table {
  border-collapse : collapse;
  border-spacing : 0;
}

(왼쪽위에있는 td) {
  border-top-left-radius : 5px;
}
```

- table 태그에 border-radius가 안먹을 때 2. 

```css
table {
  border-collapse : collapse;
  border-radius : 7px;
  border-style : hidden;
  box-shadow : 0 0 0 1px #666;
}
```

box-shadow라는 속성을 이용해 테두리를 가짜로 만들어내는 편법입니다.
box-shadow는 그림자 넣는 속성입니다.

- 상태에 따라서 스타일을 줄 수 있는 Pseudo-class 셀렉터

```css
.btn:hover {
  background : chocolate; /*마우스를 올려놓을 때*/
}
.btn:focus {
  background : red; /*클릭 후 계속 포커스 상태일 때*/
}
.btn:active {
  background : brown; /*클릭 중일 때*/
}

:any-link /*방문 전, 방문 후 링크 한번에 선택할 때*/
:playing /*동영상, 음성이 재생중일 때*/
:paused /*동영상, 음성이 정지시*/
:autofill /*input의 자동채우기 스타일*/
:disabled /*disabled된 요소 스타일*/
:checked /*체크박스나 라디오버튼 체크되었을 때*/
:blank /*input이 비었을 때*/
:valid /*이메일 input 등에 이메일 형식이 맞을 경우*/
:invalid /*이메일 input 등에 이메일 형식이 맞지 않을 경우*/
:required /*필수로 입력해야할 input의 스타일*/
:nth-child(n) /*n번째 자식 선택*/
:first-child /*첫째 자식 선택*/
:last-child /*마지막 자식 선택*/


```

pseudo-class 셀렉터를 붙이시면 여러 상태에 따른 스타일을 지정해줄 수 있습니다.
hover, focus, active 스타일 넣을 때 순서는 꼭 이렇게 선언해야 잘 동작합니다.
1. hover
2. focus
3. active
입니다. hofa로 외우면 잘외워지겠군요 
이거 말고도 수많은 pseudo-class가 있기 때문에 필요하면 찾아쓰도록 합시다.

https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes

- input 등에도 자주 사용합니다

```css
input:focus {
  border : 2px solid red;
}
```

- a 태그에도 자주 사용합니다

```css
a:link { 
  color : red; /*방문 전 링크*/ 
} 
a:visited { 
  color : black; /*방문 후 링크*/ 
} 
```

:link를 붙이면 방문 전 링크
:visited를 붙이면 방문 후 링크에 스타일을 넣을 수 있습니다.
모든 링크의 밑줄제거는 그냥 a태그에 text-decoration : none 붙이면 됩니다. 


- utility class

```css
.f-small {
    font-size: 12px;
}
```


- 코드 양을 줄이는 CSS 작성법 (OOCSS)

```css
.main-btn {
  font-size : 20px;
  padding : 15px;
  border : none;
  cursor : pointer;
}

.bg-red {
  background : red;
}
.bg-blue {
  background : blue;
}
```

버튼의 뼈대와 살을 분리하는 겁니다.
1. 버튼의 기본 스타일인 padding, font-size 이런걸 정의하는 class를 하나 만들고 
2. 버튼에 스킨 색깔놀이 하는 용도의 class를 여러개 만들어두는 겁니다.

```css
<button class="main-btn bg-red">빨간버튼</button>
<button class="main-btn bg-blue">파란버튼</button>
```

이렇게 뼈와 살을 각각의 class로 분리하는 방법의 장점은 
1. 중복된 스타일을 재사용가능합니다.
덕분에 CSS 파일용량도 줄어들고 코딩 시간도 절약됩니다.

2. 유지보수가 편리해집니다.
사이트의 모든 버튼의 font-size를 약간 줄여야한다면 이 경우엔 한 곳만 건드리면 모든 버튼이 다 수정되겠죠? 편리합니다.

3. 코드 개빨리 짤 수 있습니다.
.bg-red 이렇게 색깔놀이용 class들을 전문용어로 utility class라고 부릅니다. 
이걸 미리 많이 만들어두면 앞으로 버튼만들 때 class명을 두세개 고르기만 하면 되니까
css 파일 열지않고도 다양한 스타일을 빠르게 만들 수 있습니다.
(class명을 미리 외워두면요)

```css
.bg-red {
  background : red;
}
.bg-green {
  background : green;
}
.bg-blue {
  background : blue;
}
```

```css
.font-small {
  font-size : 12px;
}
.font-medium {
  font-size : 16px;
}
.font-lg {
  font-size : 20px;
}
```

글씨 font-size 변경이 잦다면 이런 식으로 utility class 들을 많이 만들어두고
글자 스타일링할 때 가져다 쓰면 코드짜는게 매우 빨라질 수 있습니다.
(외워두면요)
특히 width, margin, padding, text-align 이런 것들 조정하는 utility class 많이 만들어두면 편리합니다. 

지금까지 설명한 뼈와 살을 분리하는 CSS 작성방식을 Object Oriented CSS 라고 부릅니다.
어떤 아저씨가 옛날에 주장한건데 장점이 많아 실제 개발시 자주 사용합니다.
이걸 잘 쓰는 라이브러리가 Bootstrap인데 나중에 알아봅시다. 

- Block_Element--modifier
class="덩어리이름__역할--세부특징"

class wkraud 
Block_Element--modifier rule

1. class를 작명할 땐 우선 덩어리이름으로 시작하는게 좋습니다.
덩어리를 전문용어로 컴포넌트라고 하니까 그렇게 부르겠습니다.
아무튼 저는 프로필 소개하는 html 컴포넌트를 만들 것이기 때문에
거기 안에 있는 모든 class명은 일단 profile 어쩌구로 우선 작명하면 됩니다.

```css
<div class="profile">
  <img class="profile">
  <h4 class="profile">이름</h4>
  <p class="profile">소개글</p>
  <button class="profile">빨간버튼</button>
  <button class="profile">파란버튼</button>
</div>
```



2. 태그마다 다른 class명을 부여하려면 __태그명을 뒤에 붙입니다.
그니까 profile 안에 있는 img 태그는 profile__img
그니까 profile 안에 있는 button 태그는 profile__button
이렇게 __태그이름 으로 작명하라는 것입니다.
이러면 작명할 때 생각 깊게 안해도 되겠죠?
태그 이름 쓰기 싫으면 저처럼 content 이런 식으로 작명해도 봐드림 

```css
<div class="profile">
  <img class="profile__img">
  <h4 class="profile__h4">이름</h4>
  <p class="profile__content">소개글</p>
  <button class="profile__button">빨간버튼</button>
  <button class="profile__button">파란버튼</button>
</div>
```

3. 같은 태그들의 디자인을 구분하려면 --
그니까 버튼이 색깔별로 여러개가 필요하다면 
빨간 버튼은 --red
파란 버튼은 --blue 를 뒤에 붙여서 작명하라는 겁니다.
큰 버튼은 --big
작은 버튼은 --small 이렇게 맘대로 수식어를 붙이면 됩니다.

```css
<div class="profile">
  <img class="profile__img">
  <h4 class="profile__h4">이름</h4>
  <p class="profile__content">소개글</p>
  <button class="profile__button--red">빨간버튼</button>
  <button class="profile__button--blue">파란버튼</button>
</div>
```

BEM 룰을 쉽게 외우려면
Block__Element--Modifer 이런 식으로 기억해주시면 됩니다.
HTML 요소를 영어로 Element라고 하며 Modifier는 수식어라는 뜻입니다. 

근데 지금 설명한 OOCSS 클래스 작성방식, BEM 작명방식 이런건 
html css 파일이 크고 방대할 때 장점을 보이는 것이기 때문에 
요즘 React, Vue를 이용해서 웹앱을 만들 때는 크게 유용하진 않습니다.
React 이런 곳에선 html 페이지 단위가 아니라 작은 컴포넌트 단위로 개발하게 되며
class 중복되어도 컴포넌트끼리 스타일이 간섭되지 않게 코드를 짤 수 있습니다.
대표적으로 React 안에서 styled-components 라이브러리를 쓰면 그런게 가능합니다. 
그래서 요즘은 BEM 이런거 깊게 익힐 필요는 없고 여기서 설명하는 것 까지만 아셔도 충분합니다.






