---
layout: post
title: CSS - Styling 1
date: 2022-01-22 22:00:00 +0900
category: CSS
---

목차<br />
[간단한 style 등록](#간단한-style-등록)<br />
[자주 사용하는 속성](#자주-사용하는-속성)<br />
[이미지 정렬 폭 조정](#이미지-정렬-폭-조정)<br />
[텍스트의 일부만 스타일을 변경하고 싶을 때](#텍스트의-일부만-스타일을-변경하고-싶을-때)<br />


---
### 간단한 style 등록
```html
<p style="font-size : 20px; color : red"> 글자 </p>
```
+ 거의 모든 태그는 style="" 가능합니다.
+ 스타일이름 : 스타일값;
+ 세미콜론 **필수** 입니다!!

---
### 자주 사용하는 속성
```css
.box {
	font-size : 20px;
	font-family : 'gulim';
	color : black;
	letter-spacing : -1px;
	text-align : center;
	font-weight : 600;
}
```

---
### 이미지 정렬 폭 조정
```css
.image {
    display : block;
    margin-left : auto;
    margin-right : auto;
    width : 150px;
}
```
+ 이미지 가운데 정렬할 때 사용합니다.

---
### 텍스트의 일부만 스타일을 변경하고 싶을 때
```html
<p>안녕하세요 저는 <span style="color : red;">뛰어난</span> 개발자입니다.</p>
```
+ span 태그 이용해서 변경하면 됩니다.
+ span 태그 display : inline 이라는 스타일 속성이 존재 합니다.
+ display : inline을 가지고 있는 요소는 폭, 높이 등을 단독으로 결정할 수 없습니다.
+ 폭, 높이를 주고싶으면 얘를 감싸고 있는 p태그에 주시면 됩니다.