---
layout: post
title: 웹개발 부트스트랩(bootstrap) 이란? - 부트스트랩의 근본을 알아보자
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
### 한줄요약: 부트스트랩은 프론트엔드 컴포넌트 라이브러리다

### 부트스트랩이 뭔데?

트위터 개발자들이 만든건데

웹 컴포넌트(예를 들자면 버튼이나 글자나 테이블이나 폼 같은 거) 만들려면 html짜고 css넣고 하는게 귀찮기 때문에 쉽게 미리 디자인을 쭉 만들어서 라이브러리 화 해 놓고, 복붙으로 쉽게쉽게 만들 수 있게 해 주는 거다.

[https://getbootstrap.com/](https://getbootstrap.com/ "https://getbootstrap.com/")

아래는 부트스트랩 사용하는 스타터 템플릿이다.

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/css/bootstrap.min.css" integrity="sha384-zCbKRCUGaJDkqS1kPbPd7TveP5iyJE0EjAuZQTgFLD2ylzuqKfdKlfG/eSrtxUkn" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: jQuery and Bootstrap Bundle (includes Popper) -->
    <script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-fQybjgWLrvvRgtW6bFlB7jaZrFsaBXjsOMm/tB9LTS58ONXgqbR9W8oWht/amnpF" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/js/bootstrap.min.js" integrity="sha384-VHvPCCyXqtD5DqJeNxl2dtTyhF78xXNXdkwX1CZeRusQfRKp+tA7hAShOK/B/fQ2" crossorigin="anonymous"></script>
    -->
  </body>
</html>
```

### 근데 왜 이름이 부트스트랩?

부트스트랩은 부츠를 신을 때 당기는 끈을 말한다.

![](/uploads/2022-05-15-020321.jpg)

이를 사용하는 영어의 관용구는 

> pull yourself up by your bootstraps

이 있는데, 이는 부트스트랩을 당겨서 몸을 끌어올린다는 조금은 이상한 표현이다.

이 표현은 독일 소설 [_The Surprising Adventures of Baron Munchausen_](https://en.wikisource.org/wiki/The_Surprising_Adventures_of_Baron_Munchausen "wikisource: 뮌하우젠 남작의 놀라운 모험")(뮌하우젠 남작의 놀라운 모험, 국내에는 허풍선이 남작의 모험으로 출간)의 오역이 일반화된 오류이다.

허풍선이 남작은 말을 타고 가다 늪에 빠지게 되었는데, 길게 땋은 머리를 당겨서 스스로 빠져나올 수 있었다고 자랑하는데, 

![](/uploads/2022-05-15-022049.jpg)

여기서의 길게 땋은 머리가 bootstrap으로 오역되면서 위와 같은 관용구가 생기게 되었다.

### 일반적 의미의 변화

이 표현이 사용되던 초기에는 위의 내용처럼 말도 안되는 불가능한 일을 언급하는데 사용되었다.

하지만 시간이 지남에 따라 

> **사용가능한 것을 최대한 활용하는 법을 모색함**

는 뜻으로 의미가 변질되었다.

### 전문영역에서의 의미

전문 영역에서는 위의 의미를 활용하여 **_어떻게든 자력으로 해나가는 것을 뜻하거나,_**

부트스트랩을 당기면 별도의 힘을 들이지 않고 부츠를 신을 수 있는 것과 마찬가지로, **_기본(혹은 이전)자료를 이용해서 다음 자료를 도출해 내는 것을 뜻한다._** 

### 사용예

컴퓨터의 부팅이 부트스트래핑에서 유래했다.

같은 언어로 작성된 컴파일러를 부트스트래핑이라고 한다.(c언어 컴파일러는 c로 작성되었다.)

프로그램 설치시 작은 setup.exe파일이 다른 큰 설치 파일을 부르거나, 업데이트 파일을 부르거나 할 수 있는데, 시작시 불리는 작은 setup.exe파일을 부트스트랩이라 한다.

통계에서의 부트스트래핑은 통계학에서 사용된다. 이는 가설 검증(test)을 하거나 메트릭(metric)을 계산하기 전에 random sampling을 적용해서 경향을 파악해 보는 것을 말한다.

bootstrapping은 ML에서도 사용되며, 이는 랜덤 샘플링을 통해 training data를 강제로 늘리는 방법이다. **데이터 셋(training set) 내의 데이터 분포가 고르지 않은 경우 랜덤 데이터를 생성하면 분포도가 고르게 된다.**

사업에서 부트스트랩 한다는 것은 외부의 도움이나 외부자본 없이 사업을 시작하는 것을 의미한다.