---
layout: post
title: 여러대의 pc에서 깃블로그 관리하기
description: 
sitemap: false
hide_last_modified: false
categories:
- maint
- blog
tags: 

---
한줄요약: 파일공유 클라우드를 통해 할 수 있으나 설정이 복잡하므로 CMS툴을 이용하자!

그냥 [forestry.io]({% post_url 2021-08-20-what-ruby%})와 같은 CMS 툴을 사용하는 것을 추천한다. (자세한 내용은 링크를 참조.)

하지만 여러대의 PC에서 수동으로 관리하고 싶다면 아래의 과정을 거친다.

1. 깃블로그의 폴더를 파일공유 클라우드에 올린다.(구글드라이브, 원드라이브, 드롭박스 등)
2. 다른 PC등에 파일공유 데스크탑 클라이언트를 설치하고 깃블로그 폴더를 동기화 한다. (이때 on-demand로 파일을 받는 것이 아니라 모든 파일을 다운로드 하도록 한다. 파일 공유 클라우드는 디스크의 용량을 절약하기 위해 사용자의 요청이 있을 때만 해당 파일을 다운로드 하는데, 이렇게 되면 관련된 파일이 다운로드 되지 않기 때문에 에러가 발 생할 수 있다.)
3. 깃블로그 폴더로 이동하여 Jekyll과 관련된 ruby 및 번들 gem을 설치한다.
4. 깃 관리를 위해 깃블로그 폴더 내에 깃 그리고 깃헙관련 앱을 설치한다.

위와 같이 준비하면 깃블로그를 여러대의 PC에서 관리할 수 있다. 하지만 초기 설정과정이 복잡하므로 추천하지는 않는다.