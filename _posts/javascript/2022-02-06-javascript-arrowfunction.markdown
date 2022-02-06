---
layout: post
title: Javascript - Arrow function
date: 2022-02-06 22:00:00 +0900
category: Javascript
---

Arrow function
===

<br />

> 함수 선언

```javascript
(1)
function fun(){
  // write
}

(2)
var fun = function(){
  // write
}
```

<br />

> arrow function

```javascript
const fun = () => {
  // write
}
```

- 함수 기능을 직관적으로 표현

함수는 왜 사용하는가? <br />
1. 여러가지 기능을 하는 코드를 한 단어로 묶고 싶을 때 (재사용성)<br />
2. 입출력기능을 만들때<br />
함수의 소괄호안에는 input역할을 하는 파라미터가 있고<br />
함수내에 return이라는 것은 output역할을 하는 키워드입니다. <br />
소괄호에 뭔가 집어넣으면 return을 이용해 뭔가 뱉어내는 것 <br />
이게 바로 함수의 입출력 기능입니다. <br />
<br />

- 소괄호 생략

```javascript
const fun = x => { return x * 2 }
```


- 중괄호 생략

```javascript
const fun = x => x * 2;
```

<br />

> arrow function 내부 this

arrow function은 어디서 쓰든간에 내부의 this 값을 변화시키지 않습니다.<br />
상위 this의 의미를 그대로 내부에서도 사용합니다.<br />
일반 function을 항상 대체할 수 있는 문법이 아닙니다.<br />
<br />

