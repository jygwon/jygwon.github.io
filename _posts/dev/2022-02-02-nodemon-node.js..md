---
layout: post
title: 'nodemon: 파일이 저장될 때마다 node.js를 껏다켜기 귀찮을 때. '
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
**Node.js** 개발 시 자바 스크립트 파일들을 수정 할때마다 매번 ctrl+c를 통해 node를 종료 후 다시 실행해줘야 하는 번거로움 이 있었습니다.  
하지만 파일들을 모니터링하고 있다가 수정될 경우 자동으로 서버를 재실행시켜주는 스크립트 모니터링 유틸리티 **nodemon**를 이용하면 번거로움이 상당히 줄어듭니다.

(global로 적용되도록 설치)

npm install -g nodemon

그런데, 실제로 아래와 같이 실행하면 보안에러가 뜰 수 있다.

nodemon server.js

이럴 때는 파워쉘을 열어서 아래와 같이 입력한다.

Set-ExecutionPolicy unrestrcted