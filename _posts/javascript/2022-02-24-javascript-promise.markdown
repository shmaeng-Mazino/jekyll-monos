---
layout: post
title: Javascript - Promise (작성중)
date: 2022-02-24 15:00:00 +0900
category: Javascript
---

Promise
===

> ? Promise

<br />프로미스는 자바스크립트 비동기 처리에 사용되는 객체입니다.
<br />Pending(대기) : 비동기 처리 로직이 아직 완료되지 않은 상태
<br />Fulfilled(이행) : 비동기 처리가 완료되어 프로미스가 결과 값을 반환해준 상태
<br />Rejected(실패) : 비동기 처리가 실패하거나 오류가 발생한 상태

<br />

```javascript
function isPositive (number, resolve, reject) {
  setTimeout(() => {
    if(typeof number === "number") {
      // 성공 -> resolve
      resolve(number >= 0 ? "양수" : "음수");
    } else {
      // 실패 -> reject
      reject("주어진 값이 숫자형 값이 아닙니다.")
    }
  }, 2000);
}

// isPositive(
//   10, 
//   (res) => {
//     console.log("성공 : ", res);
//   },
//   (err) => {
//     console.log("실패 : ", err);
//   }
// );

function isPositiveP (number) {
  const executor = (resolve, reject) => { // 실행자
    setTimeout(() => {
      if(typeof number === "number") {
        // 성공 -> resolve
        resolve(number >= 0 ? "양수" : "음수");
      } else {
        // 실패 -> reject
        reject("주어진 값이 숫자형 값이 아닙니다.")
      }
    }, 2000);
  };

  const asyncTask = new Promise(executor);
  return asyncTask;
}

const res = isPositiveP(101);

res
  .then((res) => {
    console.log("성공 : ", res);
  })
  .catch((err) => {
    console.log("실패 : ", err);
  }
);


function taskA (a, b) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const res = a + b;
      resolve(res);
    }, 3000);
  });
  
}

function taskB (a) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const res = a * 2;
      resolve(res);
    }, 1000);
  });
  
}

function taskC (a) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const res = a * -1;
      resolve(res);
    }, 2000);
  });
  
}

// then chaining
taskA(5, 1).then((a_res) => {
    console.log('A result : ', a_res);
    return taskB(a_res);
}).then((b_res) => {
  console.log('B result : ', b_res);
  return taskC(b_res);
}).then((c_res) => {
  console.log('C result : ', c_res);
});




// taskA(3, 4, (a_res) => {
//   console.log('a result : ', a_res);
//   taskB(a_res, (b_res) => {
//       console.log('b result : ', b_res);
//       taskC(b_res, (c_res) => {
//           console.log('c result : ', c_res);
//       });
//   });
// });


```

> 에러 처리 방법

<br /> 1. then()의 두 번째 인자로 에러를 처리할 수 있다.
<br />

```javascript
taskA(5, 1).then((a_res,) => {
    console.log('A result : ', a_res);
    return taskB(a_res);
}, err);
```

<br /> 2. catch()를 이용하는 방법

```javascript
taskA(5, 1)
.then((a_res,) => {
    console.log('A result : ', a_res);
    return taskB(a_res);
})
.catch();
```


<br />
<br />
참고 (References)
<br />
[winterlood](https://www.udemy.com/course/winterlood-react-basic/)
<br />
[cotak.tistory.com](https://cotak.tistory.com/136)
