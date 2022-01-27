---
layout: post
title: CSS (position, layout)
date: 2021-01-26 22:00:00 +0900
category: css
---

position과 좌표 레이아웃 만들기
===

- 좌표속성이 있습니다.

```css
.box {
  top : 20px;
  left : 30%;
}
```

top, left, bottom, right 라는 속성을 사용하면
요소의 상하좌우 위치를 변경할 수 있습니다. 
하지만 이 좌표속성을 사용하려면 position 속성이 필요합니다. 
position 속성은 좌표속성을 적용할 기준점이 여기에요~! 라고 지정해주는 역할입니다. 


- position 속성은 크게 4개 값이 있습니다.

```css
.box {
  position : static; /* 기준이 엄서요 (좌표적용 불가) */
  position : relative; /* 기준이 내 원래 위치요 */
  position : absolute; /* 기준이 내 부모요 */
  position : fixed; /* 기준이 브라우저 창이요 (viewport) */
}
```
여기서 원하는 기준을 선택하시면 됩니다. 그럼 이제 좌표속성으로 좌표 값을 줄 수 있습니다. position : absolute는 부모 박스를 기준으로 찰싹 달라붙은 뒤에 좌표값을 적용하게 되는데, 정확히 말하면 부모가 아니라 부모 중에 position : relative를 가지고 있는 부모가 기준입니다. 


- position : absolute 를 적용한 요소 가운데 정렬 

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

적어도 5개의 속성이 있어야 가운데 정렬이 가능합니다. 
5개라니 약간 귀찮아집니다. 

- normalize.css css 초기화

하지만 박스를 만들 때 주의점이 하나 있습니다. (notion 이미지)


- 박스의 폭을 border까지 설정해주고 싶을 때 쓰는 속성 

```css
.box {
  box-sizing : border-box; /*박스의 폭은 border까지 포함입니다*/
  box-sizing : content-box; /*박스의 폭은 padding 안쪽입니다*/
}
```

box-sizing이라는 속성을 주게되면 border까지를 실제 박스의 폭으로 설정해줍니다. 
아주 고마운 속성입니다.
빨리 모든 div 박스에 추가해보도록 합시다. 









- CSS 파일 작성시 기본으로 쓰면 좋을 속성들

```css
div {
  box-sizing : border-box;
}
body {
  margin : 0;
}
html {
  line-height : 1.15; /*기본 행간 높이*/
}
```

여기에 더해서 
모든 h, p 태그의 margin을 균일하게 설정하거나
li, a 태그에 text-decoration : none 을 주거나
나중에 배울 table 태그에 border-collapse: collapse 를 주거나 
이런 것들이 가능합니다.
이런거 미리 적고 시작하면 항상 편리하게 CSS 코드를 짤 수 있습니다. 
가끔 CSS Reset 이런 식으로 부르기도 합니다.

여러분도 기본으로 복붙하고 시작할 "필수 기본값 CSS 리스트"를 하나 만들어두고 맨날 업데이트 해보십시오. 

- form은 form 태그로 만들어냅니다.

```html
<form>
  <input>
</form>
```

input태그는 닫지 않습니다. 

input의 type

```html
<input type="text">
<input type="email">
<input type="password">
<input type="radio">
<input type="file">
<input type="checkbox">
<input type="submit">
<select>
  <option>옵션1</option>
</select>
<textarea></textarea>
```
10개는 더 있지만 가장 자주 쓰는 것만 모아봤습니다. 
나머지는 필요할 때 구글에 찾아쓰도록 합시다.  

input에 넣는 속성들

```html
<input placeholder="어쩌구" value="어쩌구" name="age">
```

placeholder는 배경 글자,
value는 미리 입력된 값,
name은 서버 기능개발에 필요한 인풋의 이름을 설정 가능합니다.

HTML의 속성으로 CSS셀렉터를 사용할 수 있습니다.

```css
input[type=email] {
  color : grey
}
```

input의 type속성이 email인 요소만 찾아서 스타일을 줄 수 있습니다. 
폼에서 특히 유용하게 사용합니다. 

- 전송버튼

```html
<button type="submit">전송</button>
<input type="submit">
```

둘 중 하나 쓰시면 됩니다.
그리고 물론 `<form>` 태그 안에 있어야 잘 작동합니다.


** form & input 숙제 : Contact Us 섹션 만들기 **

```html
<form>
  <div class="w-100">
    <input>
  </div>
  <div class="w-50">
    <input>
  </div>
  <div class="w-50">
    <input>
  </div>
  <div class="w-100">
    <textarea></textarea>
  </div>
</form>
```

가로로 꽉찬 input들은 w-100 이라는 div에 싸매고,
가로로 반반 차지할 input들은 w-50 이라는 div에 싸맸습니다
그리고 w-100은 width : 100%
w-50은 width : 50%; float : left 
이렇게 주었다고 합니다. 
float 주면 당연히 어딘가에 clear : both 도 있어야겠군요

```
<input> 태그 디자인은
가로로 100% 폭을 주었고
padding 조금 주고
box-sizing : border-box
이런걸 줬습니다.
border-box 안해놓으면 폭이 padding을 포함해서 조금 커질 수 있기 때문입니다. 
```

- label 태그와 for 속성

```html
<input type="checkbox" id="subscribe">
<label for="subscribe">누르기</label>
```

label과 for 속성을 적절히 활용하면
input대신 label을 눌러도 input을 선택할 수 있습니다.
(input의 id, label의 for 속성을 똑같이 맞춰주면 됩니다)
혹은 그냥 `<input>` 에 제목이 필요할 때도 h, p 태그 이런거 말고 `<label>` 태그를 가끔 이용합니다.

