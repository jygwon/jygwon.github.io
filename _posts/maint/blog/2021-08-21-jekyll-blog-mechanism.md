---
layout: post
title: Jekyll기반 github blog 작동원리
description: ''
sitemap: false
hide_last_modified: false
categories:
- maint
- blog

---
한줄요약: 어떻게 돌아가는지 알아야 운영이 된다.

# Jekyll과 테마를 이용한 github blog 작동원리

## Jekyll이란?

지킬은 간단히 설명하자면 블로그 생성기이다.

우리가 맨땅에 처음부터 CSS, JS, HTML로 파일들을 구성하고 블로그를 만들기에는 시간도 부족하고 내용을 다 알기도 어렵고 일일이 찾기도 귀찮다. 즉 너무 힘든 일이다.

따라서 어느 정도의 형태가 갖추어져있는 블로그 템플릿을 제공받아 약간의 커스텀만 하고 포스팅하는데 집중할 수 있게 해주는 것이 Jekyll이다.

* 지킬의 특징
  * Static website 를 만들어주는 도구
  * markdown → HTML 변환해 줌
  * 수 많은 무료테마 존재
  * GitHub Pages 가 추천하는 도구

## Jekyll이 정확히 하는 일은 뭘까?

Jekyll은 다르게 말하면, 정적 컴파일러이다.

* 블로그 내 포스팅은 마크다운으로 작성되는데, 지킬은 우리가 작성한 Markdown 파일들은 _site폴더내의 HTML로 변환시킨다.
* 그리고 적용된 지킬 테마파일을 읽어서 CSS, JS등을 생성한다
* 생성된 파일들이 _site폴더(지킬 테마 내의 기본 폴더)로 이동된다. (블로그에 접근하는 사용자들은 _site폴더의 내용을 보게된다.)
* Github에 _site를 업로드하게 되면 blogname.github.io 주소에서 실행되게 된다. (하지만 소스관리도 같이 하기 때문에 보통 테마내의 모든 소스 및 포스팅 소스를 같이 올린다.)

그런데, Jekyll은 [Ruby]({% post_url 2021-08-20-what-ruby%}) 위에서 돌아간다.