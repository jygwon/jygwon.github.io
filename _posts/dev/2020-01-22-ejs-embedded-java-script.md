---
layout: post
title: 뷰모델 EJS(Embedded Java Script)란?
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
### EJS 개요

`Node.js`와 `Express`에서 많이 사용되고 있는 템플릿 엔진이다.  
`ejs`는 기존의 `HTML` 문법에 `<% %>`만 더해주면 되기 때문에(html 하고 동일)  
더욱 쉽게 서버의 데이터를 사용하거나 코드를 실행할 수 있는 장점이있다.

### EJS 설치

npm install ejs

### 기본 문법 2개만 알면 당장 쓸 수 있다

당장 쓸 것 딱 두개만 알려드리겠습니다.

    <h2><%= user.name %></h2>

HTML 중간중간에 서버 데이터를 집어넣고 싶을 땐 이렇게 사용합니다.

<%= 서버에서 보낸 데이터의 변수명 %>

그럼 HTML 글자로 렌더링 됩니다. 끝입니다.

EJS를 사용하면 HTML에 여러가지 자바스크립트 문법을 사용가능합니다.

    <% if (user) { %>
      <h2><%= user.name %></h2>
    <% } %>

HTML에 if문(또는 for문)을 적용하거나 반복문을 적용하고 싶을 땐

<% %> 내부에 자바스크립트 문법을 담으시면 됩니다.

위의 예제 코드는 user 라는 변수가 참일 때만 내부 <h2> 코드를 보여줄 것입니다.

이게 끝입니다.

### <% %> 사용 예

    // <% js 코드 %> 
    <% for(i=0; i < board.length; i++) { %>
    // <%= 변수명 %>
    <%=i+1 %>
    <a href='/board/<%= board[i]._id%>'>
    

### Include 사용 예

`<%-include('경로입력')%>`  
경로 = `header` or `footer` 등  
페이지 내 반복되는 header나 footer등의 코드는 `include`를 사용하면  
간편하게 레이아웃 작업을 할 수 있다.

    <header>
    	<% include ./header %>
    </header>
     <body>
      <p>Welcome to templating using EJS</p>
     </body>
     
    <footer>
      <% include ./footer %>
    </footer>

###   
routing 사용 예

    // 예시
    // app.js
    var express = require('express');
    var routes = require('./routes/index');
    var app = express();
    
    // view engine 템플릿 사용을 명시합니다.
    app.set('views', path.join(__dirname, 'views'));
    app.set('view engine', 'ejs');
    
    app.use('/', routes);
    app.use('/test', routes);
    
    
    // routes/index.js
    var express = require('express');
    var router = express.Router();
    
    
    // /test로 uri가 들어오면 'test'로 render,
    // title에 Hello World 출력
    router.get('/test', function(req, res) {
      res.render('test', {
      	title: 'Hello World!'
      });
    });
    
    // 모듈 내보내기
    module.exports = router;

    <!-- test.ejs -->
    <!DOCTYPE html>
    <html>
      <head>
        <title><%= title %></title>
      </head>
      <body>
        <h1><%= title %></h1>
        <p>Welcome to <%= title %></p>
      </body>
    </html>