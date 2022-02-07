---
layout: post
title: CSS - styling5 (Pseudo-class)
date: 2022-02-07 10:30:00 +0900
category: CSS
---

Pseudo-class
===

<br />

> Pseudo-class 셀렉터

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
```

pseudo-class 셀렉터를 붙이시면 여러 상태에 따른 스타일을 지정해줄 수 있습니다.<br />
hover, focus, active 스타일 넣을 때 순서는 꼭 이렇게 선언해야 잘 동작합니다.<br />
1. hover<br />
2. focus<br />
3. active<br />

<br />

```css
.btn:any-link /*방문 전, 방문 후 링크 한번에 선택할 때*/
.btn:playing /*동영상, 음성이 재생중일 때*/
.btn:paused /*동영상, 음성이 정지시*/
.btn:autofill /*input의 자동채우기 스타일*/
.btn:disabled /*disabled된 요소 스타일*/
.btn:checked /*체크박스나 라디오버튼 체크되었을 때*/
.btn:blank /*input이 비었을 때*/
.btn:valid /*이메일 input 등에 이메일 형식이 맞을 경우*/
.btn:invalid /*이메일 input 등에 이메일 형식이 맞지 않을 경우*/
.btn:required /*필수로 입력해야할 input의 스타일*/
.btn:nth-child(n) /*n번째 자식 선택*/
.btn:first-child /*첫째 자식 선택*/
.btn:last-child /*마지막 자식 선택*/
```

<br />
참고 (References)
<br />[codingapple](https://codingapple.com/)
