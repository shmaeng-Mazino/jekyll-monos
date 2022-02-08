---
layout: post
title: algorithm - 다중 포인터 (MultiplePointers)
date: 2022-02-06 05:00:00 +0900
category: algorithm
---

다중 포인터 (MultiplePointers)
===

<br />

인덱스 또는 위치에 해당하고 특정 조건에 따라 시작, 끝 또는 <br />
중간으로 이동하는 포인터 또는 값 생성 최소한의 공간 복잡성으로 <br />
문제를 해결하는 데 매우 효율적입니다.<br />
<br />

> 패턴

ex)<br />
정수의 정렬된 배열  을 받아들이는 sumZero 라는 함수를 작성하십시오. <br />
함수는 합계가 0인 첫 번째 쌍 을 찾아야 합니다. <br />
합계가 0이거나 쌍이 존재하지 않는 경우 정의되지<br />
않은 두 값을 모두 포함하는 배열을 반환합니다.<br />
<br />

```javascript
// 시간 복잡도 - O(N^2) 이중 for문
// 공간 복잡도 - O(1)
function sumZero (arr) {
    // 첫 번째 쌍 찾으면 끗
    // 왼쪽 오른쪽 더해서 0 이면 return
    // 그 외는 undefined return

    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]);
        for (let j = i+1; j < arr.length; j++) {   
            console.log(arr[j]);
            if (arr[i] + arr[j] === 0) {
                return [arr[i], arr[j]];
            }
        }
    }
}


// 리팩토링
// 시간 복잡도 - O(N)
// 공간 복잡도 - O(1)
function sumZero (arr) {
    // 첫 번째 쌍 찾으면 끗
    // 왼쪽 오른쪽 더해서 0 이면 return
    // 그 외는 undefined return

    let left = 0;
    let right = arr.length - 1;
    while (left < right) {
        let sum = arr[left] + arr[right];
        if (sum === 0) {
            return [arr[left], arr[right]];
        } else if (sum > 0) {
            right--;
        } else {
            left++;
        }
    }

}

console.log(sumZero([-3,-2,-1,0,1,2,5]))
// [-3,3] 
// sumZero([-2,0,1,3])
// undefined
// sumZero([1,2,3]) 
// undefined
```

<br />

> countUniqueValues

정렬된 배열을 받아들이고 배열의 고유한 값을 계산하는<br />
countUniqueValues 라는 함수를 구현합니다. <br />
배열에 음수가 있을 수 있지만 항상 정렬됩니다.<br />
<br />

```javascript
function countUniqueValues (arr) {

    // 중복된 값 무시하고 
    // 배열안에 숫자가 다른 값 세기

    let left = 0;
    let right = 1;

    for (let i = 0; i < arr.length; i++) {
        console.log(arr[left]);
        
        if (arr[i] === arr[right]) {
            right++;
        } else if (arr[i] !== arr[right]) {
            // console.log(arr[right]);
            left++;
            arr[left] = arr[right];
            right++;
            
        }

    }
    console.log(arr);
    return left;
}


function countUniqueValues (arr) {
    if (arr.length === 0) return 0;
    let i = 0;
    for (let j = 1; j < arr.length; j++) {
        if (arr[i] !== arr[j]) {
            i++;
            arr[i] = arr[j];
        }
        console.log(i, j);
        
    }
    return i + 1;
}

console.log(countUniqueValues([1,1,1,2,2,3,4,5,5,5,6,7]));

// console.log(countUniqueValues([1,1,1,1,1,2]));
// 2
// console.log(countUniqueValues([1,2,3,4,4,4,7,7,12,12,13]));
// 7
// console.log(countUniqueValues([]));
// 0
// console.log(countUniqueValues([-2,-1,-1,0,1]));
// 4



```

<br />
<br />
<br />

참고 (References)
<br />[udemy javascript algorithm](https://www.udemy.com/course/best-javascript-data-structures/)
