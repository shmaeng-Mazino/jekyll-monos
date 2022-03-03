---
layout: post
title: Javascript - 콜백함수
date: 2022-02-16 21:00:00 +0900
category: Javascript
---

콜백함수
===

> 콜백함수란?

<br />CallBack 함수란 이름 그대로 나중에 호출되는 함수를 말한다.
<br />콜백 함수는 코드를 통해 명시적으로 호출하는 함수가 아니라, 
<br />개발자는 단지 함수를 동록하기만 하고, 어떤 이벤트가 발생했거나
<br />특정 시점에 도달했을 때 시스템에서 호출하는 함수를 말한다.
<br />
<br />즉 콜백함수는 콜백함수라는 유니크한 문법적 특징을 
<br />가지고 있는 것이 아니라, 호출방식에 의한 구분이다.

<br />

> 이벤트 핸들러

```javascript
document.querySelector('button').addEventListener('click', function() {
			alert('버튼을 눌렀습니다.');
})
```

<br />

> setTimeout


```javascript
setTimeout(function () {
  console.log('123');
}, 2000); // 2초후 123 출력
```

<br />
<br />
참고 (References)
<br />
[winterlood](https://www.udemy.com/course/winterlood-react-basic/)
<br />
[cotak.tistory.com](https://cotak.tistory.com/136)
