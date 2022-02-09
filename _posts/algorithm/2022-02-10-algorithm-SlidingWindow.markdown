---
layout: post
title: algorithm - 슬라이딩 윈도우 (Sliding Window)
date: 2022-02-10 07:00:00 +0900
category: algorithm
---

슬라이딩 윈도우 (Sliding Window)
===

<br />

> 슬라이딩 윈도우란 ??

고정 사이즈의 윈도우가 이동하면서 윈도우 내에 있는 데이터를 <br />
이용해 문제를 풀이하는 알고리즘을 말한다. <br />
배열이나 리스트의 요소의 일정 범위의 값을 비교할때 사용하면 매우 유용하다. <br />
원래 네트워크에서 사용되던 알고리즘을 문제풀이에 응용한 경우라고 할 수 있다.<br />
<br />

> ex)

정수 배열과 n 이라는 숫자를 받아들이는 maxSubarraySum<br />
함수를 작성하십시오. <br />
함수는 배열에서 n개의 연속 요소 의 최대 합을 계산해야 합니다.<br />

```javascript
function maxSubarraySum (arr, num) {
  if(num > arr.length){
    return null;
  }

  // 최대 연속 값
  let max = 0;
  for (let i = 0; i < arr.length - num + 1; i++) {
    // 비교할 연속 값
    let temp = 0;
    for (let j = 0; j < num; j++) {
      temp += arr[i + j];
      // console.log(temp);
      if (max < temp) {
        max = temp;
      }
    }
  }
  console.log('max', max);
  return max;
}

// refactor
function maxSubarraySum (arr, num) {
  let maxSum = 0;
  let tempSum = 0;

  if (arr.length < num) {
    return null;
  }

  for (let i = 0; i < num; i++) {
    maxSum += arr[i];
  }

  tempSum = maxSum;
  
  for (let i = num; i < arr.length; i++) {
    tempSum = tempSum - arr[i - num] + arr[i];
    maxSum = Math.max(maxSum, tempSum);
  }

  console.log(maxSum);
  return maxSum;

}

// maxSubarraySum([1,2,5,2,8,1,5],2) // 10
maxSubarraySum([1,2,5,2,8,1,5],4) // 17
// maxSubarraySum([4,2,1,6],1) // 6
// maxSubarraySum([4,2,1,6,2],4) // 13
// console.log(maxSubarraySum([],4)); // null
```

참고 (References)
<br />[udemy javascript algorithm](https://www.udemy.com/course/best-javascript-data-structures/)
<br />[투 포인터 / 슬라이딩 윈도우 알고리즘](https://bbangson.tistory.com/72)
