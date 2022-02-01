---
layout: post
title: CSS - Styling 3 (Box Model)
date: 2022-02-01 20:00:00 +0900
category: CSS
---

Box Model
===

모든 HTML 요소는 Box 형태의 영역을 가지고 있다.  
Box는 콘텐트(Content), 패딩(Padding), 테두리(Border), 마진(Margin)로 구성된다.  

<img src="/public/img/css_styling3_boxmodel.png" width="450px" height="300px" title="boxmodel" alt="boxmodel" />

<br />

> Content

요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역이다. width, height 프로퍼티를 갖는다.

---
> Padding

테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역이다. padding 프로퍼티 값은 패딩 영역의 두께를 의미하며 기본색은 투명(transparent)이다. 요소에 적용된 배경의 컬러, 이미지는 패딩 영역까지 적용된다.

---
> Border

테두리 영역으로 border 프로퍼티 값은 테두리의 두께를 의미한다.

---
> Margin

테두리(Border) 바깥에 위치하는 요소의 외부 여백 영역이다. margin 프로퍼티 값은 마진 영역의 두께를 의미한다. 기본적으로 투명(transparent)하며 배경색을 지정할 수 없다.

---

```css
div {
      /* 배경색의 지정: 콘텐츠 영역과 패딩 영역에 적용된다. */
      background-color: lightgrey;
      /* 콘텐츠 영역의 너비 */
      width: 300px;
      /* 패딩 영역의 두께 */
      padding: 25px;
      /* 테두리: 두께 형태 색상 */
      border: 25px solid navy;
      /* 마진 영역의 두께 */
      margin: 25px;
    }
```

<br />

> Margin, Padding

4개의 값을 지정할 때
<br />margin: 25px 50px 75px 100px;
<br />margin-top: 25px;
<br />margin-right: 50px;
<br />margin-bottom: 75px;
<br />margin-left: 100px;

***

3개의 값을 지정할 때
<br />margin: 25px 50px 75px;
<br />margin-top: 25px;
<br />margin-right: 50px; margin-left: 50px;
<br />margin-bottom: 75px

***

2개의 값을 지정할 때
<br />margin: 25px 50px;
<br />margin-top: 25px; margin-bottom: 25px;
<br />margin-right: 50px; margin-left: 50px;

***

1개의 값을 지정할 때
<br />margin: 25px;
<br />margin-top: 25px; margin-right: 25px; margin-bottom: 25px; margin-left: 25px;

<br />

> border

```css
/* border-style 프로퍼티는 테두리 선의 스타일을 지정한다. */

p.dotted { border-style: dotted; }
p.dashed { border-style: dashed; }
p.solid  { border-style: solid; }
p.double { border-style: double; }
p.groove { border-style: groove; }
p.ridge  { border-style: ridge; }
p.inset  { border-style: inset; }
p.outset { border-style: outset; }
p.none   { border-style: none; }
p.hidden { border-style: hidden; }
p.mix    { border-style: dotted dashed solid double; }

/* 프로퍼티 값의 갯수에 따라 4개 방향(top, right, left, bottom)에 대하여 지정이 가능하다. */

p.d1 {
	/* four sides */
	border-style: dashed;
}
p.d2 {
	/* horizontal | vertical */
	border-style: dotted solid;
}
p.d3 {
	/* top | horizontal | bottom */
	border-style: hidden double dashed;
}
p.d4 {
	/* top | right | bottom | left */
	border-style: none solid dotted dashed;
}
```

> border-radius

```css
.border-rounded {
	/* 4 꼭지점에 대해 Radius 지정 */
	border-radius: 5px;
}
.border-circle {
	border-radius: 50%;
}
.border-football {
	/* top-left & bottom-right | top-right & bottom-left */
	border-radius: 15px 75px;
}

.border-rounded {
	border-radius: 20px;

	/* 위 코드는 아래의 shorthand이다.
	border-top-left-radius:     20px;
	border-top-right-radius:    20px;
	border-bottom-right-radius: 20px;git
	border-bottom-left-radius:  20px;
	*/
}
```

<br />
참고 (References)
<br />[poiemaweb.com](https://poiemaweb.com/css3-selector)
