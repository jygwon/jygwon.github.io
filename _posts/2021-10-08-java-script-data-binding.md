---
layout: post
title: 자바 스크립트 배열 자료형과 데이터 바인딩 feat. arrow function(애로우 펑선)
description: ''
sitemap: false
hide_last_modified: false
categories: []
tags: ''

---
* toc
{:toc .large-only}
  
  
  
Java Script Data Binding 
한줄요약: 데이터 다루려면 필수로 알아야 한다.

## 근데, 이런거 왜 쓰는데?

```{javascript, attr.source='.numberLines'}
    var car = '소나타';
    var carPrice = 50000;
    var carColor = 'white';
```

갑자기 여러 데이터들을 변수에 저장할 일이 생겼습니다.

그럼 코드 위처럼 짜도 되겠지만

자료가 몇십개면 변수도 몇십개 귀찮게 만들어야겠군요.

그냥 한 변수에 여러개의 자료를 저장하는 방법도 있습니다. 이럴 때 배열 자료형을 씁니다.

## 자바 스크립트의 배열 자료형

### **Array 자료형**

여러가지 자료를 한곳에 **순서대로** 저장하고 싶을 때 사용하는 자료형입니다.

    var car = ['소나타', 50000, 'white'];

대괄호를 열고 자료를 콤마로 구분해서 집어넣으면 됩니다.

그럼 여러 자료를 엑셀처럼 저장가능

    var car = ['소나타', 50000, 'white'];
    console.log(car[1]);

array 자료에서 데이터 뽑을 땐 대괄호를 뒤에 붙이면 됩니다.

\[x\] 라고 쓰면 x번째 자료를 출력해줍니다.

    var car = ['소나타', 50000, 'white'];
    car[1] = 60000;
    console.log(car[1]);

array 자료를 수정하고 싶으면 등호 이용해서 수정하면 됩니다.

자료 추가도 됩니다.

그래서 결론은 여러 자료를 변수 하나에 **순서대로** 저장하고 싶으면 array를 사용하면 편리합니다.

### **Object 자료형**

이것도 여러가지 자료를 한곳에 저장하고 싶을 때 사용하는 자료형입니다.

    var car2 = { name : '소나타', price : 50000 };

중괄호를 열고 자료를 콤마로 구분해서 집어넣으면 됩니다.

그런데 자료 왼쪽에 자료의 이름을 붙여서 저장해야합니다.

멋진 말로 자료의 이름은 key, 실제 자료는 value라고 부릅니다.

그래서 object 자료형은 key : value 형태로 자료를 저장할 수 있습니다.

이름붙여주니 구분하기 편리한듯

    var car2 = { name : '소나타', price : 50000 };
    console.log(car2['name']);
    console.log(car2.name);

array 자료에서 데이터 뽑을 땐 대괄호를 뒤에 붙이면 되는데

\[자료이름\] 이렇게 써야합니다.

.자료이름 이렇게 써도 가능합니다. 마음에드는거 쓰십쇼

    var car2 = { name : '소나타', price : 50000 };
    car2['name'] = '그랜저';
    console.log(car2['name']);

object 자료를 수정하고 싶으면 등호 이용해서 수정하면 됩니다.

자료 추가도 됩니다.

그래서 결론은 여러 자료를 변수 하나에 저장하고 싶으면 object 사용해도 편리합니다.

### **Array/Object 차이 - 이름(키)**

그래서 둘 중 아무거나 골라서 맘대로 쓰면 되는데

**상품명, 가격, 연식, 색상, 옵션여부, 카드할인여부 ... (뒤에 10개 더 있음)**

이런 데이터를 변수하나에 보관하고 싶으면 array 쓸 것입니까 object 쓸 것입니까

저라면 object 사용할 것 같습니다.

    var car = ['소나타', 50000, 2030, 'white', false];

▲ array쓰면 저장시엔 간단하겠지만

나중에 자료 뽑을 때 약간 어렵습니다.

가격뽑을 때 **"가격자료가 몇번째 위치에 있었지?**" 를 기억해내야합니다.

    var car = { name : '소나타', price : 50000, year : 2030 };

▲ object로 넣으면 저장은 귀찮겠지만

가격뽑을 때 **"가격의 key 이름이 뭐였지"** 를 기억하면 됩니다.

여러분이 컴퓨터가 아니라 인간이면 순서기억보다 key값 기억해내는게 훨씬 쉬울겁니다.

이런 차이점이 있으니 array 쓸지 object 쓸지 잘 고민해봅시다.

### **Array/Object 차이 - 순서**

array는 순서개념이 있습니다. 왼쪽에 적을 수록 더 앞에 있는 자료임

object는 순서개념이 없습니다. 가장 왼쪽에 적었다고 해도 1빠임을 보장해주지 않습니다.

그래서 array 자료는 순서개념이 있다보니

**- 가나다순 정렬**

**- x번 자료부터 x번 자료까지 자르기**

**- x번 자료 바꾸기**

**- 맨 뒤, 맨 앞에 자료 넣기**

**- 원하는 자료가 들어있나 검색**

순서개념이 필요한 많은 것들을 할 수 있습니다.

array자료.sort() 하면 가나다순 정렬되고

array자료.slice(x, y) 하면 x번부터 y번 전까지 자를 수 있고

array자료.push(x) 하면 x를 맨 뒤에 입력할 수 있고

이런 기본함수들이 준비되어있습니다.

array 자료 조작이 필요할 때 검색해서 써보도록 합시다.

## 자료를 뽑아보자.

### 모양새로 뽑는 방법을 판단

아래와 같은 데이터에서 상품명을 뽑는 법을 알아봅시다.

    var products = [
      { id : 0, price : 70000, title : 'Blossom Dress' },
      { id : 1, price : 50000, title : 'Springfield Shirt' },
      { id : 2, price : 60000, title : 'Black Monastery' }
    ]; 

어렵게 생긴 자료도 console.log 해보면 쉽게 출력할 수 있다고 했습니다.

console.log(products) 해보면 **\[{ }, { }, { }\]** 이렇게 나옵니다.

그냥 array 안에 object 3개가 들어있을 뿐입니다.

그래서 저기서 내가 원하는 자료를 뽑고 싶으면 시작 기호만 잘 보면 됩니다.

> **\[로 시작하면, array**
>
> **\[ 이거는 array라서 인덱싱하면 됩니다.**
>
> **{로 시작하면, object**
>
> **{ 이거는 object라서 이름불러주면 됩니다.**

이번엔 console.log(products\[0\]) 해보면 **{ id : 0, price : 70000, title : 'Blossom Dress' }** 이런게 나옵니다.

{ 이거는 object라서 이름불러주면 됩니다.

여기서 Blossom Dress 뽑으려면

**console.log(products\[0\].title)**

이렇게 쓰면 잘나올듯요

### **뽑은 자료 가공하기**

    console.log('가격: ' + 뽑은자료 );  // '가격: 2000'출력됨

자바스크립트에서 덧셈기호 쓰면 문자이어붙이기가 쉽게 가능합니다.

**숫자 + 숫자**는 숫자 덧셈해주는데

**문자 + 숫자**처럼 적어도 1개가 문자면  문자2개 이어붙여줌

    var a = '안녕';
    console.log('문자' + a + '문자');  // '문자안녕문자'출력됨

그래서 문자중간에 변수넣고 싶으면 덧셈기호 저렇게 활용하면 됩니다.

### 백틱기호(')와 중간에 변수 넣기

    var a = '안녕';
    console.log(`문자 ${a} 문자`);  // '문자안녕문자'출력됨

귀찮으면 여러분 키보드 물결기호 밑에 있는 백틱기호 쓰면 됩니다.

백틱기호도 문자만들어주는데

> **1. 문자 중간에 엔터키 칠 수 있음**
>
> **2. 중간에 ${ 변수명 } 문법을 이용가능함**
>
> **${ } 이건 문자안에 변수넣어주는 간단한 문법입니다.**
>
> **일반 따옴표안에선 사용불가능합니다.**

## 뽑은 자료를 돌려보자

배열형으로 만든 자료는 당연히 돌리게 되어 있습니다.

쭉 돌리면서 쭉 뿌려주던지,

쭉 돌리면서 원하는 걸 뽑던지.

그래서 돌릴 줄 알아야 합니다.

![](/uploads/download-1.jpg)

(돌리고\~ 돌리고)

### **array에는 forEach 반복문**

array 자료 뒤에 붙일 수 있는 forEach() 라는 기본함수가 있습니다.

이것도 반복문임

    var pants = [28, 30, 32];
    pants.forEach(function(){
      console.log('안녕')
    });

이렇게 쓰면 pants 안의 데이터 갯수만큼

forEach 콜백함수 안에 있는 코드가 실행됩니다.

3번 실행될듯요

그래서 array 자료 다룰 때 for 반복문 쓰기 귀찮으면 forEach 뒤에 붙여도 됩니다.

> **Q. 콜백함수 왜넣음?**
>
> A. 아몰랑\~ 자바스크립트 forEach 만든 사람이 그렇게 쓰래요

    var pants = [28, 30, 32];
    pants.forEach(function(a, i){
      console.log(a);
      console.log(i);
    });

콜백함수 안에 파라미터 2개까지 작명이 가능한데 (실은 3개까지인데 몰라도 됩니다)

* 첫 파라미터는 **반복문 돌 때 마다 array 안에 있던 하나하나의 데이터**가 되고
* 둘 째 파라미터는 **반복문 돌 때 마다 0부터 1씩 증가하는 정수**가 됩니다.

  <script>
  var pants = \[28, 30, 32\];
  $('.form-select').eq(0).on('input', function(){

        var value = $('.form-select').eq(0).val();
        if (value == '셔츠') {
          $('.form-select').eq(1).removeClass('form-hide');
        }
        else if (value == '바지'){
          $('.form-select').eq(1).removeClass('form-hide');
          $('.form-select').eq(1).html('');
          pants.forEach(function(a){
            $('.form-select').eq(1).append(`<option>${a}</option>`)
          })
        }
      
      });

  </script>

▲ 그래서 아까 코드도 이렇게 바꿔봤습니다.

이제 pants 라는 서버에서 보낸 데이터가 바뀔 때 마다

거기에 맞게 <option>이 생성되겠군요. 변화에 대응이 좋은 코드가 되었습니다.

### **object에는 for in 반복문**

object 자료 갯수만큼 반복문을 돌리고 싶으면

    var obj = { name : 'kim', age : 20 }
    
    for (var key in obj){
      console.log('안녕')
    }

for in 반복문 쓰면 됩니다.

그럼 콘솔창에 '안녕'이 2회 출력될듯요

그리고 for in 반복문 쓰면 object 자료 안에 있는 key와 value를 다 출력해볼 수도 있습니다.

지금 key라고 작명하는 부분은 반복문이 돌 때 마다 object자료 안에 있던 key값이 됩니다.

    var obj = { name : 'kim', age : 20 }
    
    for (var key in obj){
      console.log(key)
    }

출력해보면 진짜로 name, age 잘 나옵니다.

key 말고 실제 자료인 value를 출력하고 싶으면

console.log(obj\[key\]) 이렇게 써보셈

### **반복문의 용도는 2가지**

코드 복사붙여넣기용으로 쓰는게 for 반복문이라 했는데

array나 object 자료 전부 꺼내서 쓰고 싶을 때도 반복문을 쓰면 유용합니다.

그래서 딱 페이지 내의 코드를 봤는데,

1\. 코드복붙하고싶으면

2\. array, object 자료 다 꺼내고 싶을 때

반복문 사용하면 유용합니다.

### **arrow function 문법**

함수 만드는 다른 문법이 있습니다. 특히 콜백함수만들 때 자주 쓰는 방법인데

    var pants = [28, 30, 32];
    pants.forEach(function(a){
      console.log(a)
    });
    
    pants.forEach((a) => {
      console.log(a)
    });

function 키워드 대신 => 화살표를 ( ) 우측에 부착해도 똑같이 함수만들 수 있습니다.

저걸 arrow function 이라고 합니다.

긴 단어 타이핑 하기 싫은 귀차니스트 개발자들을 위해 생긴것 입니다.

    pants.forEach( a => {
      console.log(this)
    });

arrow function은 파라미터가 하나면 () 소괄호 생략해도 봐줍니다.

함수 중괄호 안에 return 한 줄 밖에 없으면 { } 중괄호와 return 동시에 생략해도 봐줍니다.

그래서 간결하니 콜백함수에 자주 사용하는 사람들이 있습니다.

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