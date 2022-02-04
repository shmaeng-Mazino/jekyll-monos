---
layout: post
title: Javascript - this
date: 2022-02-04 15:00:00 +0900
category: Javascript
---

this
===
<br />

> window

```javascript
// 로그
console.log(this);

function fun () {
    console.log(this);
}
```

window는 모든 전역변수, 함수, DOM을 보관하고 관리하는 전역객체입니다. grobal object<br />
<br />
IE 10버전 이상에선 **'use strict'**라는 키워드를 페이지 최상단에 추가하면<br />
strict mode로 자바스크립트를 작성가능합니다. <br />
strict mode에선 var 키워드 없이 변수를 선언하거나, <br />
변수를 arguments라는 이상한 키워드로 선언하거나 그런 실수를 방지해줍니다. <br />
strict mode에선 this 키워드를 일반함수 안에서 불렀을 때 undefined라는 값으로 강제로 지정해줍니다. <br />
<br />

> object 자료형

```javascript
const obj = {
    data : 'mazino',
    fun : function () {console.log(this)}
}

obj.fun();
```

objcjet 메소드안에서 this를 쓰시면 this는 메소드를 가지고 있는 오브젝트를 뜻합니다.<br />
{ data : 'mazino', fun : f }<br />
<br />

> constructor

```javascript
function init(){
  this.name = 'Kim'
}
var obj = new init();
```

constructor 안에서 쓰면 constructor로 새로생성되는 오브젝트를 뜻합니다. <br />


<br />

> event listener e.currentTarget

```javascript
document.getElementById('btn).addEventListener('click', function(e){
  console.log(this)
});
```

이벤트 리스너 안에서 this를 소환하면 이것은 바로 e.currentTarget이라는 뜻과 똑같은 의미입니다. <br />
e.currentTarget은 지금 이벤트가 동작하는 곳을 뜻합니다. <br />





















