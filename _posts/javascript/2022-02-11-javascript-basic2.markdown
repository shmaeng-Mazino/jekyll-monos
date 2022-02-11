---
layout: post
title: Javascript - 비구조화 할당
date: 2022-02-07 15:00:00 +0900
category: Javascript
---

비구조화 할당
===

<br />

> 비구조화 할당이란?

배열이나 객체 속성을 해체하여 개별 변수에 값을 담을 수 있는 JavaScript 표현식을 말합니다.<br />
또는 구조 분해 할당이라고 명칭 합니다.<br />
<br />

> 기본 문법

비구조화 할당의 기본 구조는 좌측에는 변수, 우측에는 해당 변수에 넣어지는 값을 표현합니다.<br />
배열의 경우 []를 사용하고, 객체의 경우 {}를 사용한다.<br />

```javascript
let [x,y] = [1,2];
console.log(x);
console.log(y);

let {x,y} = {x: 1, y:2};
console.log(x);
console.log(y);
```

<br />

> 비구조화 할당의 장점은?

배열, 객체 내 값을 추출하는 코드가 매우 간단해진다.<br />
필요한 객체와 나머지 요소 분리가 매우 간단하다.<br />
기본값 지정이 가능하다.<br />

<br />

> 간단한 코드 정리

- 비구조화할당 전 코드
각각 배열 안에 있는 요소들을 꺼내 쓰기 위해서 각각의 변수 안에 배열 내 숫자를 찾아서 매칭 시켜줘야 했다.<br />

```javascript
let fruit = ['Apple', 'Banana', 'Peach'];

let Apple = fruit[0];
let Banana = fruit[1];
let Peach = fruit[2];

console.log(Apple);
console.log(Banana);
console.log(Peach);
```

반면 비구조화 할당 코드를 이용하면 한 줄로 해당 배열의 코드를 바로 객체 안에 넣어주는 것이 가능하다.<br />
비구조화 할당코드를 이용하면 왼쪽의 변수에 오른쪽 배열 값이 바로 값을 분해해서 바로 할당해준다. <br />

``` javascript
let fruit = ['Apple', 'Banana', 'Peach'];
let [Apple,Banana, Peach] = fruit;

console.log(Apple);
console.log(Banana);
console.log(Peach);
```

<br />

> 비구조화할당 구조 분해

만약에 1:1로 값이 매칭 되는 것이 아니라, <br />
하나의 값은 변수에 넣고 나머지는 나머지 변수에 할당도 가능하다.<br />
전개 연산자인... 을 이용하면 매칭 된 값 외 모든 데이터 값을 할당할 수 있다.<br />

```javascript
let fruit = ['Apple', 'Banana', 'Peach', 'Pear'];
let [Apple, ...etc] = fruit;

console.log(Apple);
console.log(etc);
```

<br />

... 을 이용하면 하나의 변수를 할당하고 나머지 값들을 모두 넣어준다.<br />
... 인 전개 연산자를 사용하려면, 반드시 가장 마지막 요소에 넣어줘야 한다.<br />
<br />

> 기본값 지정

만약 내가 지정한 변수보다 넣어줄 매칭 할 값이 없다면 undefined가 발생한다.<br />
만약 이때 undefined가 아니라 기본적으로 넣어주는 값이 있다고 하면 기본 값 을지 정하는 것도 가능하다.<br />

```javascript
let fruit = ['Apple', 'Banana', 'Peach'];
let [Apple,Banana, Peach, Pear='Pear'] = fruit;

console.log(Apple);
console.log(Banana);
console.log(Peach);
console.log(Pear);
```

<br />
<br />
참고 (References)
<br />[devrappers](https://devrappers.tistory.com/41?category=856235)
<br />[winterlood](https://www.udemy.com/course/winterlood-react-basic/)
<br />[김평범's OrdinaryCode](https://ordinary-code.tistory.com/115)
