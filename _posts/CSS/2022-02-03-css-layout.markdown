---
layout: post
title: CSS - layout, position, 좌표
date: 2022-02-03 13:00:00 +0900
category: CSS
---

layout
===

사이트 레이아웃 디자인의 제 1원칙 : 모든 요소를 네모박스로 쪼개어 생각하면 된다.<br />

> 요소를 공중에 띄워 왼쪽/오른쪽 정렬하는 float 속성

```html
<div>
  <div class="left-box"></div>
  <div class="right-box"></div>
</div>
```
```css
.left-box {
  width : 100px; 
  height : 100px;
  float : left;
}
.right-box {
  width : 100px; 
  height : 100px;
  float : left;
}
```

위의 코드는 박스 두개를 만들어 각각 왼쪽으로 정렬합니다. <br />
float을 쓰면 요소를 붕 띄우다보니 그 다음에 오는 HTML 요소들이 제자리를 찾지 못하니 <br />
float 박스들을 묶는 하나의 큰 div 박스를 만들고 폭을 지정해주는게 좋습니다.<br />

> float를 쓰고 나면 항상 clear 속성이 필요합니다.

```html
<div>
  <div class="left-box"></div>
  <div class="right-box"></div>
  <div class="footer"></div>
</div>
```
```css
.footer {
  clear : both
}
```

clear 속성을 사용하면 float 다음에 오는 박스들이 제자리를 찾게 됩니다.<br />

position, 좌표
===

> 좌표속성

```css
.box {
  top : 20px;
  left : 30%;
}
```

top, left, bottom, right 라는 속성을 사용하면<br />
요소의 상하좌우 위치를 변경할 수 있습니다. <br />
하지만 이 좌표속성을 사용하려면 position 속성이 필요합니다. <br />
position 속성은 좌표속성을 적용할 기준점이 여기에요~! 라고 지정해주는 역할입니다. <br />

> position 속성은 크게 4개 값이 있습니다.

```css
.box {
  position : static; /* 기준이 없음 (좌표적용 불가) */
  position : relative; /* 기준이 내 원래 위치 */
  position : absolute; /* 기준이 내 부모 */
  position : fixed; /* 기준이 브라우저 창이 (viewport) */
}
```

여기서 원하는 기준을 선택하시면 됩니다. 그럼 이제 좌표속성으로 좌표 값을 줄 수 있습니다.<br />
position : absolute는 부모 박스를 기준으로 찰싹 달라붙은 뒤에 좌표값을 적용하게 되는데, <br />
정확히 말하면 부모가 아니라 부모 중에 **position : relative**를 가지고 있는 부모가 기준입니다. <br />

> position : absolute 를 적용한 요소 가운데 정렬 

```css
.button {
  position : absolute; 
  left : 0;
  right : 0; 
  margin-left : auto;
  margin-right : auto;
  width : 적절히
}
```


<br />
참고 (References)
<br />[codingapple](https://codingapple.com/)
