---
layout: post
title: 이벤트리스너 안에서 쓰는 이벤트 함수들 e, this
description: ''
sitemap: false
hide_last_modified: false
categories: []
tags: ''

---
### 이벤트리스너 안에서 쓰는 이벤트 함수들

    document.querySelector('.black-bg').addEventListener('click', function(e){
      e.target;
      e.currentTarget;
      e.preventDefault();
      e.stopPropagation();
    })

이벤트리스너의 콜백함수에 파라미터 아무거나 추가하면

이벤트관련 유용한 함수들을 사용가능합니다.

파라미터 이름은 아무렇게나 작명하면 됩니다. 보통 대충 e라고 함

**e.target**은 실제 클릭한 요소 알려줌 (이벤트 발생한 곳)

**e.currentTarget**은 지금 이벤트리스너가 달린 곳 알려줌 (참고로 this라고 써도 똑같음)

**e.preventDefault()** 실행하면 이벤트 기본 동작을 막아줌

**e.stopPropagation()** 실행하면 내 상위요소로의 이벤트 버블링을 중단해줌

몇개만 뽑아봤는데 필요할 때 가져다가 쓰면 됩니다.

여기서 중요한건 e.target인데

이벤트 버블링이 일어난다고 해도

사용자가 실제로 클릭한 그 요소는 저 문법으로 찾아낼 수 있다는걸 기억해둡시다.