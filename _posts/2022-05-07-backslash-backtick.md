---
layout: post
title: 자바스크립트 \(백슬래시, backslash), `(백틱, backtick)를 이용한 특수문자 처리방법
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
한줄요약: 이스케이프 문자를 알자.

~~~
<script>
//아래와 같은 문장을 출력하고자 할 때,
//he said "Hi, my name is Tom."
console.log("he said "Hi, my name is Tom." "); //에러
console.log("he said "Hi, my name is Tom." "); //백슬래쉬
console.log(`he said "Hi, my name is Tom."`); //백틱
</script>
~~~

자바스크립트에서 특수문자를 출력할 때,
\\나 백틱(\`)을 사용해서 처리해줘야 하는데
이를 이스케이프 처리라고 하고, 앞에 오는 특수문자를 이스케이프 문자라고 한다.

특수문자 앞에 \\를 넣어주면 다음에 오는 특수문자가 문자 그대로 출력 된다.

문자열을 `로 둘러싸면` \`로 싸여진 모든 글자가 문자열로 처리되게 된다.

이러한 이스케이프 처리는 모든 프로그래밍 **언어마다 사용하는 이스케이프 문자**가 있으므로 숙지하자.