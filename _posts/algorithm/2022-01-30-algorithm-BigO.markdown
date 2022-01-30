---
layout: post
title: algorithm - 빅오표기법, 시간복잡도, 공간복잡도
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

<img src="/public/img/BigO_O(1).png" width="450px" height="300px" title="BigO" alt="O(1)" />

```javascript
function addUpTo(n) {
  return n * (n + 1) / 2;
}
```

<br />

> O(n)

O(n)은 선형 복잡도(linear complexity)라고 부르며, 입력값이 증가함에 따라
<br />시간 또한 같은 비율로 증가하는 것을 의미한다.
<br />예를 들어 입력값이 1일 때 1초의 시간이 걸리고, 입력값을 100배로 증가시켰을 때
<br />1초의 100배인 100초가 걸리는 알고리즘을 구현했다면,
<br />그 알고리즘은 O(n)의 시간 복잡도를 가진다고 할 수 있다.

<img src="/public/img/BigO_O(n).png" width="450px" height="300px" title="BigO" alt="O(n)" />

```javascript
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
```

<br />

> O(log n)

O(log n)은 로그 복잡도(logarithmic complexity)라고 부르며,
<br />Big-O표기법중 O(1) 다음으로 빠른 시간 복잡도를 가진다.
<br />BST(Binary Search Tree)에선 원하는 값을 탐색할 때, 
<br />노드를 이동할 때마다 경우의 수가 절반으로 줄어든다.
<br />이해하기 쉬운 게임으로 비유해 보자면 up & down을 예로 들 수 있다.
<br />1~100 중 하나의 숫자를 플레이어1이 고른다. (30을 골랐다고 가정한다.)
<br />50(가운데) 숫자를 제시하면 50보다 작으므로 down을 외친다.
<br />경우의 수를 계속 절반으로 줄여나가며 정답을 찾는다.
<br />매번 숫자를 제시할 때마다 경우의 수가 절반이 줄어들기 때문에 
<br />최악의 경우에도 7번이면 원하는 숫자를 찾아낼 수 있게 된다.
<br />BST의 값 탐색 또한 이와같은 로직으로, O(log n)의 시간 복잡도를 가진 알고리즘(탐색기법)이다.

<img src="/public/img/BigO_O(log n).png" width="450px" height="300px" title="BigO" alt="O(log n)" />

```javascript
function numberOfHalves(n) {
  var count = 0;
  while (n > 1) {
    n /= 2;
    count++;
  }
  return count;
}

```

<br />

> O(n2)

O(n2)은 2차 복잡도(quadratic complexity)라고 부르며, 
<br />입력값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가하는 것을 의미한다.
<br />예를 들어 입력값이 1일 경우 1초가 걸리던 알고리즘에 5라는 값을 주었더니 25초가 걸리게 된다면, 
<br />이 알고리즘의 시간 복잡도는 O(n2)라고 표현한다.

<img src="/public/img/BigO_O(n2).png" width="450px" height="300px" title="BigO" alt="O(n2)" />

```javascript
function printAllPairs(n) {
  for (var i = 0; i < n; i++) {
    for (var j = 0; j < n; j++) {
      console.log(i, j);
    }
  }
}
```

<br />

> O(2n)

O(2n)은 기하급수적 복잡도(exponential complexity)라고 부르며, 
<br />Big-O 표기법 중 가장 느린 시간 복잡도를 가진다.
<br />종이를 42번 접으면 그 두께가 지구에서 달까지의 거리보다 커진다는 이야기를 들어보신 적 있으신가?
<br />고작 42번 만에 얇은 종이가 그만한 두께를 가질 수 있는 것은, 매번 접힐 때마다 두께가 2배 로 늘어나기 때문이다.
<br />구현한 알고리즘의 시간 복잡도가 O(2n)이라면 다른 접근 방식을 고민해 보는 것이 좋다.

<img src="/public/img/BigO_O(2n).png" width="450px" height="300px" title="BigO" alt="O(2n)" />

```javascript
function fibonacci(n) {
  if (n <= 1) {
    return 1;
  }
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```

<br />
<br />
<br />

참고 (References)
<br />[noahlogs.tistory.com](https://noahlogs.tistory.com/27)
<br />[hanamon.kr](https://hanamon.kr/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-time-complexity-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84/)