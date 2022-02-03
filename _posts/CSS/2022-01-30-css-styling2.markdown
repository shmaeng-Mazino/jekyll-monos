---
layout: post
title: CSS - Styling 2 (Selector)
date: 2022-01-30 20:00:00 +0900
category: CSS
---

CSS Selector
===

> Selector

```css
Selector {Property:Property value;}
```

> 종류

```css
/* 단수 */
h1 { color: red; }
p  { color: blue; }

/* 복수 : 쉼표( , )로 구분 */
h1, p { color: red; }

/* 전체 셀렉터 (Universal Selector)
> 모든 요소를 선택 */
* { color: red; }

/* 태그 셀렉터 (Type Selector)
> 모든 p 태그 요소를 선택 */
p { color: red; }

/* ID 셀렉터 (ID Selector)
> id 어트리뷰트 값이 p1인 요소를 선택 */
#p1 { color: red; }

/* 클래스 셀렉터 (Class Selector)
> class 어트리뷰트 값이 container인 모든 요소를 선택
> color 어트리뷰트는 자식 요소에 상속된다. */
.container { color: red; }
/* not supported in IE 
initial : 초기화 */
#p2 { color: initial; }

/* 어트리뷰트 셀렉터 (Attribute Selector)
/* 셀렉터[어트리뷰트] 
> a 요소 중에 href 어트리뷰트를 갖는 모든 요소*/
a[href] { color: red; }

/* 셀렉터[어트리뷰트=”값”]
> a 요소 중에 target 어트리뷰트의 값이 "_blank"인 모든 요소 */
a[target="_blank"] { color: red; }

/* 셀렉터[어트리뷰트~=”값”]
> h1 요소 중에 title 어트리뷰트 값에 "first"를 단어로 포함하는 요소 */
h1[title~="first"] { color: red; }

/* 셀렉터[어트리뷰트|=”값”] 
> p 요소 중에 lang 어트리뷰트 값이 "en"과 일치하거나 "en-"로 시작하는 요소 */
p[lang|="en"] { color: red; }

/* 셀렉터[어트리뷰트^=”값”] 
> a 요소 중에 href 어트리뷰트 값이 "https://"로 시작하는 요소 */
a[href^="https://"] { color: red; }

/* 셀렉터[어트리뷰트$=”값”]
> a 요소 중에 href 어트리뷰트 값이 ".html"로 끝나는 요소 */
a[href$=".html"] { color: red; }

/* 셀렉터[어트리뷰트*=”값”] */
/* div 요소 중에서 class 어트리뷰트 값에 "test"를 포함하는 요소 */
div[class*="test"] { color: red; }
/* div 요소 중에서 class 어트리뷰트 값에 "test"를 단어로 포함하는 요소 */
div[class~="test"] { background-color: yellow; }

/* 복합 셀렉터 (Combinator) */
/* 후손 셀렉터 (Descendant Combinator) 
> div 요소의 후손요소 중 p 요소 */
div p { color: red; }

/* 자식 셀렉터 (Child Combinator)
> div 요소의 자식요소 중 p 요소 */
div > p { color: red; }

/* 인접 형제 셀렉터(Adjacent Sibling Combinator)
> p 요소의 형제 요소 중에 p 요소 바로 뒤에 위치하는 ul 요소를 선택한다. */
p + ul { color: red; }

/* 일반 형제 셀렉터(General Sibling Combinator) 
> p 요소의 형제 요소 중에 p 요소 뒤에 위치하는 ul 요소를 모두 선택한다.*/
p ~ ul { color: red; }

/* 가상 클래스 셀렉터 (Pseudo-Class Selector) */
selector:pseudo-class {
  property: value;
}

/* 
:link		| 셀렉터가 방문하지 않은 링크일 때
:visited	| 셀렉터가 방문한 링크일 때
:hover		| 셀렉터에 마우스가 올라와 있을 때
:active		| 셀렉터가 클릭된 상태일 때
:focus		| 셀렉터에 포커스가 들어와 있을 때
*/

/* a 요소가 hover 상태일 때 */
a:hover { color: red; }

/* input 요소가 focus 상태일 때 */
input:focus { background-color: yellow; }

/* a 요소가 방문하지 않은 링크일 때 */
a:link { color: orange; }

/* a 요소가 방문한 링크일 때 */
a:visited { color: green; }

/* a 요소에 마우스가 올라와 있을 때 */
a:hover { font-weight: bold; }

/* a 요소가 클릭된 상태일 때 */
a:active { color: blue; }

/* text input 요소와 password input 요소에 포커스가 들어와 있을 때 */
input[type=text]:focus,
input[type=password]:focus {
	color: red;
}

/* UI 요소 상태 셀렉터(UI element states pseudo-classes) */
/*
:checked		| 셀렉터가 체크 상태일 때
:enabled		| 셀렉터가 사용 가능한 상태일 때
:disabled		| 셀렉터가 사용 불가능한 상태일 때
*/

/* input 요소가 사용 가능한 상태일 때,
	input 요소 바로 뒤에 위치하는 인접 형제 span 요소를 선택 */
input:enabled + span {
	color: blue;
}
/* input 요소가 사용 불가능한 상태일 때,
	input 요소 바로 뒤에 위치하는 인접 형제 span 요소를 선택 */
input:disabled + span {
	color: gray;
	text-decoration: line-through;
}
/* input 요소가 체크 상태일 때,
	input 요소 바로 뒤에 위치하는 인접 형제 span 요소를 선택 */
input:checked + span {
	color: red;
}

/* 구조 가상 클래스 셀렉터(Structural pseudo-classes) */
/*
:first-child - 셀렉터에 해당하는 모든 요소 중 첫번째 자식인 요소를 선택한다.
:last-child - 셀렉터에 해당하는 모든 요소 중 마지막 자식인 요소를 선택한다.
*/
/* p 요소 중에서 첫번째 자식을 선택 */
p:first-child { color: red; }

/* p 요소 중에서 마지막 자식을 선택 */
/* body 요소의 두번째 p 요소는 마지막 자식 요소가 아니다.
	body 요소의 마지막 자식 요소는 div 요소이다. */
p:last-child { color: blue; }

/*
:nth-child(n)		| 셀렉터에 해당하는 모든 요소 중 앞에서 n번째 자식인 요소를 선택한다.
:nth-last-child(n)	| 셀렉터에 해당하는 모든 요소 중 뒤에서 n번째 자식인 요소를 선택한다.
*/
/* ol 요소의 자식 요소인 li 요소 중에서 짝수번째 요소만을 선택 */
ol > li:nth-child(2n)   { color: orange; }
/* ol 요소의 자식 요소인 li 요소 중에서 홀수번째 요소만을 선택 */
ol > li:nth-child(2n+1) { color: green; }

/* ol 요소의 자식 요소인 li 요소 중에서 첫번쨰 요소만을 선택 */
ol > li:first-child     { color: red; }
/* ol 요소의 자식 요소인 li 요소 중에서 마지막 요소만을 선택 */
ol > li:last-child      { color: blue; }

/* ol 요소의 자식 요소인 li 요소 중에서 4번째 요소 요소만을 선택 */
ol > li:nth-child(4)    { background: brown; }

/* ul 요소의 모든 자식 요소 중에서 뒤에서부터 시작하여 홀수번째 요소만을 선택 */
ul > :nth-last-child(2n+1) { color: red; }
/* ul 요소의 모든 자식 요소 중에서 뒤에서부터 시작하여 짝수번째 요소만을 선택 */
ul > :nth-last-child(2n)   { color: blue; }

/*
:first-of-type - 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 첫번째 등장하는 요소를 선택한다.
:last-of-type - 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 마지막에 등장하는 요소를 선택한다.
:nth-of-type(n) - 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 앞에서 n번째에 등장하는 요소를 선택한다.
:nth-last-of-type(n) - 셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 뒤에서 n번째에 등장하는 요소를 선택한다.
*/

/* p 요소의 부모 요소의 자식 요소 중 첫번째 등장하는 p 요소 */
p:first-of-type  { color: red; }
/* p 요소의 부모 요소의 자식 요소 중 마지막 등장하는 p 요소 */
p:last-of-type   { color: blue; }
/* p 요소의 부모 요소의 자식 요소 중 앞에서 2번째에 등장하는 p 요소 */
p:nth-of-type(2) { color: green; }
/* p 요소의 부모 요소의 자식 요소 중 뒤에서 2번째에 등장하는 p 요소 */
p:nth-last-of-type(2) { color: orange;}

/* 부정 셀렉터(Negation pseudo-class) */
/* :not(셀렉터) - 셀렉터에 해당하지 않는 모든 요소를 선택한다. */
/* input 요소 중에서 type 어트리뷰트의 값이 password가 아닌 요소를 선택 */
input:not([type=password]) {
	background: yellow;
}
/* div 요소 중에서 1, 4, 7...번째 등장하는 요소가 아닌 요소만을 선택 */
/* 1, 4, 7... : 공차가 3인 등차수열 */
div:not(:nth-of-type(3n+1)) {
	margin-left: 2%;
}
/* div 요소 중에서 4번째 이후 등장하는 요소가 아닌 요소만을 선택 */
div:not(:nth-of-type(n+4)) {
	margin-bottom: 2%;
}

/* 정합성 체크 셀렉터(validity pseudo-class) */
/*
:valid(셀렉터) - 정합성 검증이 성공한 input 요소 또는 form 요소를 선택한다.
:invalid(셀렉터) - 정합성 검증이 실패한 input 요소 또는 form 요소를 선택한다.
*/
input[type="text"]:valid {
	background-color: greenyellow;
}

input[type="text"]:invalid {
	background-color: red;
}
/*
<label>입력값이 반드시 필요
	<input type="text" required>
</label>
<br>
<label>특수문자를 포함하지 않는 4자리 문자 또는 숫자
	<input type="text" value="ab1!"	pattern="[a-zA-Z0-9]{4}" required>
</label>
<br>
<label>핸드폰 번호 형식
	<input type="text" value="010-1111-2222" pattern="^\d{3}-\d{3,4}-\d{4}$" required>
</label>
*/

/* 가상 요소 셀렉터 (Pseudo-Element Selector) */
/*
::first-letter - 콘텐츠의 첫글자를 선택한다.
::first-line - 콘텐츠의 첫줄을 선택한다. 블록 요소에만 적용할 수 있다.
::after - 콘텐츠의 뒤에 위치하는 공간을 선택한다. 일반적으로 content 프로퍼티와 함께 사용된다.
::before - 콘텐츠의 앞에 위치하는 공간을 선택한다. 일반적으로 content 프로퍼티와 함께 사용된다.
::selection - 드래그한 콘텐츠를 선택한다. iOS Safari 등 일부 브라우저에서 동작 않는다.
*/

/* p 요소 콘텐츠의 첫글자를 선택 */
p::first-letter { font-size: 3em; }
/* p 요소 콘텐츠의 첫줄을 선택 */
p::first-line   { color: red; }

/* h1 요소 콘텐츠의 앞 공간에 content 어트리뷰트 값을 삽입한다 */
h1::before {
	content: " HTML!!! ";
	color: blue;
}
/* h1 요소 콘텐츠의 뒷 공간에 content 어트리뷰트 값을 삽입한다 */
h1::after {
	content: " CSS3!!!";
	color: red;
}

/* 드래그한 콘텐츠를 선택한다 */
::selection {
	color: red;
	background: yellow;
}

```

<br />

참고 (References)
<br />[poiemaweb.com](https://poiemaweb.com/css3-selector)
