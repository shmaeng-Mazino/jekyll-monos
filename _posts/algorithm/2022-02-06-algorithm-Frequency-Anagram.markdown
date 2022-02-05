---
layout: post
title: algorithm - 문제 해결 패턴 (빈도수 세기, 아나그램)
date: 2022-02-06 05:00:00 +0900
category: algorithm
---

문제 해결 패턴 (빈도수 세기, 아나그램)
===

<br />

> 빈도수 세기 패턴

이 패턴은 개체 또는 집합을 사용하여 값/값의 빈도를 수집합니다.<br />
이것은 종종 배열/문자열을 사용하여 중첩 루프 또는 O(N^2) 작업의 필요성을 <br />
피할 수 있습니다.<br />

<br />
ex) 두 개의 배열을 허용하는 same 이라는 함수를 작성하십시오.<br />
배열의 모든 값이 두 번째 배열의 해당 값을 제곱한 경우 함수는 <br />
true를 반환해야 합니다. 값의 빈도는 동일해야 합니다.<br />
<br />

```javascript
// 시간 복잡도 - N^2
function same(arr1, arr2) {
    if (arr1.length !== arr2.length) {
        return false;
    }
    for (let i = 0; i < arr1.length; i++) {
        let correctIndex = arr2.indexOf(arr1[i] ** 2);
        if (correctIndex === -1) {
            return false;
        }
        arr2.splice(correctIndex, 1);
    }
    return true;
}

// 리팩토링
// 시간 복잡도 - O(n)
function same(arr1, arr2) {
    if (arr1.length !== arr2.length) {
        return false;
    }
    let frequencyCounter1 = {};
    let frequencyCounter2 = {};
    for (let val of arr1) {
        frequencyCounter1[val] = (frequencyCounter1[val] || 0) + 1;
    }
    for (let val of arr2) {
        frequencyCounter2[val] = (frequencyCounter2[val] || 0) + 1;
    }

    console.log(frequencyCounter1);
    console.log(frequencyCounter2);

    for (let key in frequencyCounter1) {
        if (!(key ** 2 in frequencyCounter2)) {
            return false;
        }
        if (frequencyCounter2[key ** 2] !== frequencyCounter1[key]) {
            return false;
        }
    }
    return true;
}

same([1,2,3], [4,1,9]) // true
same([1,2,3], [1,9]) // false
same([1,2,1], [4,4,1]) // false (must be same frequency)
```

<br />

> 아나그램

ex) 두 개의 문자열이 주어지면 두 번째 문자열이 첫 번째 문자열의 아나그램인지 <br />
확인하는 함수를 작성하십시오. <br />
<br />

```javascript
function validAnagram(first, second) {
    // add whatever parameters you deem necessary - good luck!

    if (first.length !== second.length) {
        return false;
    }

    const lookup = {};

    for (let i = 0; i < first.length; i++) {
        let letter = first[i];
        // if letter exists, increment, otherwise set to 1
        lookup[letter] ? (lookup[letter] += 1) : (lookup[letter] = 1);
    }
    console.log(lookup);

    for (let i = 0; i < second.length; i++) {
        let letter = second[i];
        // can't find letter or letter is zero then it's not an anagram
        if (!lookup[letter]) {
            return false;
        } else {
            lookup[letter] -= 1;
        }
    }
}

validAnagram('', ''); // true
validAnagram('aaz', 'zza'); // false
validAnagram('anagram', 'nagaram'); // true
validAnagram('rat', 'car'); // false) // false
validAnagram('awesome', 'awesom'); // false
validAnagram('qwerty', 'qeywrt'); // true
validAnagram('texttwisttime', 'timetwisttext'); // true
```

<br />
<br />
<br />
