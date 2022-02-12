---
layout: post
title: Javascript - 동기, 비동기, 블로킹, 논블로킹 (작성중)
date: 2022-02-10 14:00:00 +0900
category: Javascript
---

동기, 비동기, 블로킹, 논블로킹
===

<br />

> 동기(Synchronous)

현재 작업의 응답이 끝남과 동시에 다음 작업이 요청된다. <br />
함수를 호출하는 곳에서 호출되는 함수가 결과를 반환할 때까지 기다린다.<br />
작업 완료 여부를 계속해서 확인한다.<br />
<br />

>비동기(Asynchronous)

현재 작업의 응답이 끝나지 않은 상태에서 다음 작업이 요청된다.<br />
함수를 호출하는 곳에서 결과를 기다리지 않고, <br />
다른 함수(callback)에서 결과를 처리한다.<br />
작업 완료 여부를 확인하지 않는다.<br />
<br />

> 블로킹(Blocking), 논블로킹(Non-Blocking)

블로킹/논블로킹은 주로 멀티 스레딩, I/O 등에서 사용되는 개념이며, <br />
함수의 리턴 시점과 제어권에 따라 차이가 난다.<br />
<br />

**- 블로킹(Blocking)**<br />
제어권이 호출된 함수에게 넘어가서 호출된 함수 내에서 작업이 모두 끝난 후 <br />호출한 함수에게 다시 제어권이 넘어온다.<br />
작업이 완료된 후 새로운 작업을 수행할 수 있다.<br />
<br />

**- 논블로킹(Non-Blocking)**<br />
제어권이 계속 호출한 함수에 있기 때문에 작업의 완료여부와 관계없이 새로운 <br />작업을 수행할 수 있다.<br />
<br />

<br />
<br />
참고 (References)
<br />
[winterlood](https://www.udemy.com/course/winterlood-react-basic/)
<br />
[cotak.tistory.com](https://cotak.tistory.com/136)
