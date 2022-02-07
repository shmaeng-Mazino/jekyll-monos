---
layout: post
title: Javascript - Truthy & Falsy, 삼항, 단축 평가 논리 계산법, 조건문 업그레이드
date: 2022-02-07 14:00:00 +0900
category: Javascript
---

Truthy & Falsy, 삼항, 단축 평가 논리 계산법, 조건문 업그레이드
===

<br />

> Truthy & Falsy

Truthy와 Falsy는 자바스크립트의 문법이 아닌 자바스크립트의 특성입니다.<br />
Truthy는 말 그대로 True같은 것, Falsy는 False같은 것으로 보여지는 값은 <br />
true나 false가 아니지만 자바스크립트가 true나 false로 이해하는 값들을 의미합니다. <br />

<br />

```javascript
let a = "";
// Truthy : {}, 123, "0", "false", Infinity
// Falsy : null, "", undefined, a;, 0, -0, NaN
if (a) {
    console.log('TRUE');
} else {
    console.log('FALSE');
}

const getName = (person) => {
    if (!person) { // false NOT => True
        return "객체 아님";
    }
    return person.name;
}

let person = { name: "Mazino" };
const name = getName(person);
console.log(name);
```

<br />

> 삼항 연산자

<br />

```javascript
let a = 3;
if (a >= 0) {
    console.log('양수');
} else {
    console.log('음수');
}

a >= 0 ? console.log('양수') : console.log('음수');

let b = [];

if (b.length === 0) {
    console.log('temp array');
} else {
    console.log('not temp array');
}

const c = b.length === 0 ? "temp array" : "not temp array";
console.log(c);

let d = [];

const result = d ? true : false;
console.log(result);
```

<br />

> 단축 평가 논리 계산법

- && AND 연산자

```javascript
const dog = {
    name: null
}

function getName (animal) {
    if (animal) {
        return animal.name;
    }

    return undefined;
}

const name = getName(dog);
console.log('name', name);
```

<br />

```javascript
const dog = {
    name: '멍멍이'
};
  
function getName(animal) {
    return animal && animal.name;
}

const name = getName(dog);
console.log(name);
```

&& AND연산자는 양쪽값 모두가 true일 경우 true를 반환하는 연산자입니다.<br />
<br />
&&는 양쪽 값 모두 true여야 true를 반환하고<br />
위의 값을 보시면 animal이 있기때문에 true이고 <br />
animal.name이 있기때문에 true입니다.<br />
이럴때 AND연산자는 뒷 항의 값을 반환하는 특성을 가지고 있습니다.<br /> 
앞에 값이 true고 뒤에 값도 true다 하면 뒤에 값을 반환하는 특성을 가지고 있습니다.<br />
<br />
&&연산자는 즉 앞이 false일 경우 그냥 앞의 false를 반환하고 <br />
앞이 true일 경우 뒤에 있는 항을 반환하는 특성을 가지고 있습니다. <br />
<br />

> || OR 연산자


```javascript
const namelessDog = {
    name: ''
}

function getDogName(animal) {
    const name = animal && animal.name;
    if (!name) {
         return '이름이 없는 동물입니다.'
    }
    return name;
}

const name = getName(namelessDog);
console.log(name);
```

<br />

```javascript
const namelessDog = {
    name: ''
}

function getDogName(animal) {
    const name = animal && animal.name;

    return name || '이름이 없는 동물입니다.';
}

const name = getDogName(namelessDog);
console.log(name);
```

OR연산자는 앞의 값이 false면 뒤에 있는 값을 반환하고<br />
앞의 값이 true면 앞에 있는 값을 반환합니다.<br /> 
위 예시에서는 이름이 있을 경우에는 이름을 <br />
없을 경우에는 '이름이 없는 동물입니다.'를 반환합니다.<br />
<br />

> 조건문 업그레이드 (조건문을 더 스마트하게 쓰는 방법)

```javascript
const isAnimals = (text) => ['고양이', '개', '거북이', '너구리'].includes(text);

const meal = {
    한식: "불고기",
    양식: "스테이크",
    일식: "초밥",
    중식: "꿔바로우",
    인도식: "카레"
  };
  
  const getMeal = (mealType) => {
    return meal[mealType] || "굶기";
  };
  
  console.log(getMeal("중식"));
  console.log(getMeal());

```





<br />
<br />
참고 (References)
<br />[devrappers](https://devrappers.tistory.com/41?category=856235)
<br />[winterlood](https://www.udemy.com/course/winterlood-react-basic/)