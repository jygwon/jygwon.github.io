---
layout: post
title: github 계정생성 및 블로그 호스팅
description: >
sitemap: false
hide_last_modified: false
categories:
  - maint
tags: github blog pat token
---

github 계정 생성
github personal access token 생성
생성한 토큰은 안전한 곳에 보관하고 공유하지 않는다.

github 레포지토리 생성
이름은 blogname.github.io
위 이름이 블로그의 url이 된다.


지킬이 설치된 폴더로 이동해서
git bash나 power shell내에서 아래와 같이 입력한다.

git init
git add --a
git commit -m 'first'
git remote add origin https://github.com/jodygwon/jodygwon.github.io.git
git push -u origin master

위와 같이 하면 pat를 입력하는 윈도우가 나오는데 거기에 전에 생성한 pat를 넣어준다.
혹시 pat윈도우가 나오지 않고 에러가 떨어지면 아래와 같이 적어준다.

git remote set-url origin https://jodygwon:your_actual_pat@github.com/jodygwon/jodygwon.github.io.git
git push -u origin master
