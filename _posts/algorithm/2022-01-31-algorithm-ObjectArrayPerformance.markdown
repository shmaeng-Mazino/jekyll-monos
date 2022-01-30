---
layout: post
title: algorithm - 배열과 객체의 성능 분석
date: 2022-01-31 07:00:00 +0900
category: algorithm
---

배열과 객체의 성능 분석
===

<br />

> 객체(Objects)

객체는 순서가 없지만 key와 value을 사용해 빠르다는 장점이 있다.
<br />Big-O로 보는 성능은 다음과 같다.
<br />
<br />삽입(Insertion) - O(1)
<br />삭제(Removal) - O(1)
<br />검색(Searching) - O(N)
<br />접근(Access) - O(1)
<br />
<br />객체 메소드들의 Big-O
<br />Object.keys - O(N)
<br />Object.values - O(N)
<br />Object.entries - O(N)
<br />hasOwnProperty - O(1) (Access개념이므로)
<br />hasOwnProperty를 제외한 나머지 메소드들은 Obejct에 할당된 모든
<br />데이터들을 1번은 순회해야하므로 Linear한 complexity를 갖는다.

<br />

> 배열

순서가 있는 목록으로, 순서가 필요할 때 사용하는 자료구조이다.
<br />빠른 접근이 가능하다.
<br />index만 있으면 특정 data의 위치에 접근할 수 있기 때문에 접근은 일정하다.(constant) - O(1)
<br />검색은 Object와 마찬가지로 Linear하다 O(N)
<br />
<br />배열의 메소드들과 시간복잡도
<br />Array.push - O(1) : 끝에 추가하는 것이므로 constant
<br />Array.pop - O(1) : 끝에 빼는 것이므로 constant
<br />Array.shift - O(N) :
<br />Array.unshift - O(N)
<br />Array.concat - O(N)
<br />Array.slice - O(N)
<br />Array.splice - O(N)
<br />Array.sort - O(N*log N)
<br />Array.forEach/map/filter/reduce/etc. - O(N)

<br />
