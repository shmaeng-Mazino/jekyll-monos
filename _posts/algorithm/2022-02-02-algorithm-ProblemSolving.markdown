---
layout: post
title: algorithm - 문제 해결 방식
date: 2022-02-02 06:00:00 +0900
category: algorithm
---

문제 해결 방식
===

<br />

> 문제의 이해 Understand The Problem

ex) 두 개의 숫자를 받아 합을 반환하는 함수를 작성하십시오.<br />
<br />
내 자신의 말로 문제를 다시 말할 수 있습니까?<br />
"두개 변수를 받아 더하기를 한다"<br />
문제에 들어가는 입력은 무엇입니까?<br />
"int? float? string?"<br />
문제에 대한 솔루션에서 나와야 하는 출력은 무엇입니까?<br />
"int? float? string?"<br />
입력에서 출력을 결정할 수 있습니까? 다시 말해, <br />
나는 문제를 해결하기에 충분한 정보를 가지고 있습니까? <br />
"상황에 따라 다르다. 질문을 할수있는 환경인지 아니면 예시가 있던지"<br />
문제의 일부인 중요한 데이터 조각에 어떻게 레이블을 지정해야 합니까?<br />
<br />

> 예시를 구체적으로 살펴본다 Explore Examples

간단한 예제 작성<br />
더 복잡한 예제로 진행<br />
빈 입력이 있는 예제 탐색<br />
잘못된 입력이 있는 예제 탐색<br />
<br />

> 진행 단계에 대해 순차적으로 작성한다 (Break It Down)

문자열을 받아서 문자열의 각 문자의 개수를 반환하는 함수를 작성하십시오.<br />
```javascript
charCount("hello");
{
    h: 1,
    e: 1,
    l: 2,
    o: 1
}

function charCount (str) {
/*
마지막에 반환할 빈 객체를 만든다
문자열의 각 문자를 돌면서
만약 객체에 해당 문자가 이미 들어갔으면, 문자의 개수에 1을 더한다
만약 객체에 해당 문자가 없다면, 객체에 더해주고 값을 0으로 지정한다
객체를 반환한다
*/
}
```

<br />

> 문제해결 및 단순화

하고자 하는 일의 핵심적인 어려움을 찾아라<br />
그 어려움을 일시적으로 무시<br />
우선적으로 단순화된 솔루션 작성<br />
그런 다음 그 어려움을 다시 고민하고 통합한다.<br />
<br />

```javascript
function charCount (str) {
    // 마지막에 반환할 빈 객체를 만든다
    const result = {};

	// 문자열의 각 문자를 돌면서
    for (let i = 0; i < str.length; i++) {
        const char = str[i];
        // 만약 객체에 해당 문자가 이미 들어갔으면, 문자의 개수에 1을 더한다
        if (result[char] > 0) {
            result[char]++;
        // 만약 객체에 해당 문자가 없다면, 객체에 더해주고 값을 1으로 지정한다
        } else {
            result[char] = 1;
        }
    
    }
    // 객체를 반환한다
    return result;
	
}
```

<br />

> 리팩토링

결과를 확인할 수 있습니까?<br />
결과를 다르게 도출할 수 있습니까?<br />
한 눈에 이해가 되시나요?<br />
결과나 방법을 다른 문제에 사용할 수 있습니까?<br />
솔루션의 성능을 향상시킬 수 있습니까?<br />
리팩토링하는 다른 방법을 생각할 수 있습니까?<br />
다른 사람들은 이 문제를 어떻게 해결했습니까?<br />
<br />

```javascript
// 리팩토링 1
function charCount (str) {
    const result = {};
    for (let i = 0; i < str.length; i++) {
        const char = str[i].toLowerCase();
        if (/[a-z0-9]/.test(char)) {
            result[char] = ++result[char] || 1;
        }
    }
    return result;
	
}

// 리팩토링 2
// charCodeAt 사용해서 함수 분리
function charCount(str) {
    const result = {};
    for (let char of str) {
      if (isAlphaNumeric(char)) {
        char = char.toLowerCase();
        result[char] = ++result[char] || 1;
      }
    }
    return result;
}
  
function isAlphaNumeric(char) {
    const code = char.charCodeAt(0);
    if (
      !(code > 47 && code < 58) && // numeric(0-9)
      !(code > 64 && code < 91) && // upper alphabet(A-Z)
      !(code > 96 && code < 123) // lower alphabet(a-z)
    ) {
      return false;
    }
    return true;
}

console.log(charCount("hello"));
```

<br />
<br />

참고 (References)
<br />[https://velog.io/@jangws](https://velog.io/@jangws/)
<br />