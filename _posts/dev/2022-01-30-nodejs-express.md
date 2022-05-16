---
layout: post
title: node.js용 express 라이브러리 란?
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
express 사이트([https://expressjs.com](https://expressjs.com "https://expressjs.com"))에 가보면, express란

> **_'Node.js를 위한 빠르고 개방적인 간결한 웹 프레임워크'_**

라고 한다.

뭔소린지...

이전 포스트에 NodeJS란, 자바스크립트를 브라우저 밖에서 사용하게 해주는 프로그램이라고 했다.

어떤 개발자가 NodeJS를 사용해서 서버를 만들고자 한다. 그렇다면 무엇을 해야할까? HTTP 통신을 해야하니까.. HTTP 통신 방법도 배워야 하고, 패킷에 정보를 실어보내야 하니까, 패킷 구조도 배워야 하고, 음.. HTTP통신이 3핸드쉐이킹이었나 뭐였나.... 포기!😂

그래서 훌륭하신 어떤분께서 이런걸 미리 다 만들어 놓으셨다.

express란, NodeJS를 사용하여 서버를 개발하고자 하는 개발자들을 위하여 서버를 쉽게 구성할 수 있게 만든 프레임워크다. (프레임워크란, 클래스와 라이브러리의 집합체)

### 정의: 한줄요약

**express란 NodeJS를 사용하여 쉽게 서버를 구성할 수 있게 만든 프레임웍이다**

### 설치

express의 설치에 앞서, 두 가지를 선행해야 한다.

1. NodeJS의 설치, 그리고
2. 두npm init을 통한 프로젝트 initialize가

그리고, npm install express 명령어로 express를 설치.

### 사용

서버를 만들고 포트를 열어보자.

    const express = require('express')
    const app = express()
    const port = 8080
    
    app.get('/', (req, res) => {
      res.send('Hello World!')
    })
    
    app.listen(port, () => {
      console.log(`Example app listening at http://localhost:${port}`)
    })

포트 8080에 그 유명한 헬로월드 메시지 확인할 수 있다.![](https://velog.velcdn.com/images%2Fmadpotato1713%2Fpost%2F1cc08d2e-5309-4a82-815d-2abf6add5b4e%2Fimage.png)