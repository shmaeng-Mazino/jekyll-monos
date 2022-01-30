---
layout: post
title: algorithm - 빅오표기법, 시간복잡도, 공간복잡도 (작성중)
date: 2022-01-30 17:00:00 +0900
category: algorithm
---

algorithm - 빅오표기법, 시간복잡도, 공간복잡도
===

<br />

> Big-O 표기법 (big-O notation)

빅오 표기법은 알고리즘의 효율성을 표기해주는 표기법이다.
<br />알고리즘의 효율성은 데이터 개수(n)가 주어졌을 때 덧셈, 뺄셈, 곱셈 같은 기본 연산의 횟수를 의미한다.
<br />빅오 표기법은 보통 알고리즘의 시간 복잡도와 공간 복잡도를 나타내는데 주로 사용 된다.
<br />시간 복잡도는 알고리즘의 시간 효율성을 의미하고, 
<br />공간 복잡도는 알고리즘의 공간(메모리) 효율성을 의미한다.
<br />시간과 공간 복잡도를 나타내는 방법으로는 점근 표기법이라고 해서
<br />빅오(Big-O), 빅오메가(big-Ω),빅세타(big-Θ) 표기법이 있다.

<br />

> Big-O 표기법의 종류

1. O(1)
2. O(n)
3. O(log n)
4. O(n2)
5. O(2n)

<br />

<img src="/public/img/BigO.png" width="450px" height="300px" title="BigO" alt="BigO" />

<br/>

> Big-O 표기법 예제

1. O(1) : 스택에서 Push, Pop
2. O(log n) : 이진트리
3. O(n) : for 문
4. O(n log n) : 퀵 정렬(quick sort), 병합정렬(merge sort), 힙 정렬(heap Sort)
5. O(n2): 이중 for 문, 삽입정렬(insertion sort), 거품정렬(bubble sort), 선택정렬(selection sort)
6. O(2n) : 피보나치 수열

<br />

> O(1)

O(1)는 일정한 복잡도(constant complexity)라고 하며, 입력값이 증가하더라도 시간이 늘어나지 않는다.
<br />입력값의 크기와 관계없이, 즉시 출력값을 얻어낼 수 있다는 의미이다.

<img src="/public/img/BigO_O(1).png" width="450px" height="300px" title="BigO" alt="BigO" />

```javascript
function addUpTo(n) {
  return n * (n + 1) / 2;
}
```



