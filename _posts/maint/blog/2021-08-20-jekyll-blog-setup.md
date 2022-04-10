---
layout: post
title: Jekyll과 테마를 이용한 github blog 셋업
description: >
sitemap: false
hide_last_modified: false
categories:
  - maint
  - blog
---

  한줄요약: 내용이 많아서 축약해 놓았다.

복잡한 내용이 있으나 간단한 셋업 방법을 적겠다.

1. 필요한 소프트웨어 설치
  - VS Code
  - Atom(추가 패키지 설치 필요)
    - 패키지 매니저를 사용하면 좋다.(여기 참조)
    - 관련 패키지는 다음 문서를 확인. (여기 참조)
  - Git
  - Ruby (루비는 다음 버전을 받는다.Ruby+Devkit 2.7.5-1 (x64))
  - Jekyll테마 - HydeJack
  - Github Desktop(옵션)
  - Source Tree(옵션)


2. 설정
  - vs code터미널에서
  - gem install bundler jekyll (관련된 gem패키지를 설치)
  - bundle install (관련된 패키지를 설치)
  - bundle exec jekyll serve (jekyll블로그를 실행)
    - 120.0.0.1:4000 으로 실행된다.

3. github blog 동기화
  - 로컬에서 잘 돌아가는 걸 확인했으면 gitblog로 호스팅 해 보자.
  - gitblog 계정만들고 호스팅하기
  - 소스 푸쉬
