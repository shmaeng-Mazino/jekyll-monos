---
layout: post
title: CSS - Cross browser (작성중)
date: 2022-02-09 15:10:00 +0900
category: CSS
---

Cross browser
===

<br />

> 조건부로 익스플로러 버전용 CSS파일 첨부

```html
<!--[if lt IE 9]>
  <link rel="stylesheet" type="text/css" href="css/ie8.css" />
<![endif]-->
```

위 파일은 인터넷 익스플로러 9 미만에서만 적용됩니다.<br />
저걸 [if lt IE 10] 이렇게 바꾸면 익스플로러 10 미만에서만 적용됩니다.<br />

<br />

참고 (References)
<br />[codingapple](https://codingapple.com/)
