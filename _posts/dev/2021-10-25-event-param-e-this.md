---
layout: post
title: 이벤트리스너 안에서 쓰는 이벤트 함수들 e, this
description: ''
sitemap: false
hide_last_modified: false
categories: []
tags: ''

---
# e

지식채널 e 아님.

```html
    document.querySelector('.black-bg').addEventListener('click', function(e){
      e.target;
      e.currentTarget;
      e.preventDefault();
      e.stopPropagation();
    })
```

이벤트리스너의 콜백함수에 파라미터 아무거나 추가하면

이벤트관련 유용한 함수들을 사용가능합니다.

파라미터 이름은 아무렇게나 작명하면 됩니다. 보통 대충 e라고 적습니다.

* **e.target**은 실제 클릭한 요소 알려줌 (이벤트 발생한 곳)
* **e.currentTarget**은 지금 이벤트리스너가 달린 곳 알려줌 (참고로 this라고 써도 똑같음)
* **e.preventDefault()** 실행하면 이벤트 기본 동작을 막아줌
* **e.stopPropagation()** 실행하면 내 상위요소로의 이벤트 버블링을 중단해줌

몇개만 뽑아봤는데 필요할 때 가져다가 쓰면 됩니다.

**_여기서 젤 중요한건 e.target인데_**

이벤트 버블링이 일어난다고 해도

사용자가 실제로 클릭한 그 요소는 저 문법으로 찾아낼 수 있다는걸 기억해둡시다.

# this

this는 자기자신을 가리키는 키워드로 일반적인 언어에서는 객체나 함수 자신을 가리킨다.(파이썬, c# 등)

그런데 javascript에서는 일반적으로 전역변수(최상위 객체인 window)를 가리킨다.

하지만 좀 더 구체적으로 보면, javascript에서의 this는 아래와 같은 4가지 형태가 있다.

1. 그냥 아무렇게나 사용된 경우 ->최상위 객체인 window를 가리킨다.
2. 함수 내에 사용된 경우 -> 최상위 객체인 window를 가리킨다.
3. 객체나 컴포넌트 내에 사용되고 객체가 인스턴스화 된 경우 -> 객체나 컴포넌트 자신을 가리킨다.
4. 비동기처리에 사용된 경우 -> 화살표 문법에서 사용된 경우는 객체나 컴포넌트 자신을 가리킨다. 하지만 일반 function에서 사용된 경우는 undefine이 리턴된다. (그래서 일반 펑션에서는 펑션 밖에서 this를 별도 변수로 받아서 펑션에서 해당 변수를 사용하게 된다.) 그러니까 웬만하면 그냥 화살표 문법을 사용하자.