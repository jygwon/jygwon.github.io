---
layout: Java Script Arrow Function 문법
title: ''
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
함수 만드는 다른 문법이 있습니다. 특히 콜백함수만들 때 자주 쓰는 방법인데

    var pants = [28, 30, 32];
    pants.forEach(function(a){
      console.log(a)
    });
    
    pants.forEach((a) => {
      console.log(a)
    });

**function 키워드** 대신 => **화살표를 ( ) 우측**에 부착해도 똑같이 함수만들 수 있습니다.

저걸 arrow function 이라고 합니다.

    pants.forEach( a => {
      console.log(this)
    });

arrow function은 파라미터가 하나면 () 소괄호 생략해도 봐줍니다.

함수 중괄호 안에 return 한 줄 밖에 없으면 { } 중괄호와 return 동시에 생략해도 봐줍니다.

그래서 간결하니 콜백함수에 자주 사용하는 사람들이 있습니다.

여러분도 쓰고싶으면 쓰셈

    let 함수 = function(){ console.log('안녕') }
    let 함수 = () => { console.log('안녕') }

참고로 함수 이렇게 만들어쓰는 사람도 있습니다.

이럴 때도 arrow function이 가끔 보입니다.

그냥 함수와 arrow function의 기능차이는 하나가 있는데

함수 안에서 this를 써야할 경우

\- 그냥 함수는 함수 안에서 this를 알맞게 재정의해줍니다.

\- arrow function은 함수 안에서 this를 재정의해주지 않고 바깥에 있던 this를 그대로 씁니다.

그래서 이벤트리스너 콜백함수안에서 this를 써야하면 arrow function 쓰면 의도와 다르게 동작할 수도 있습니다.

그런데선 쓰지마십시오