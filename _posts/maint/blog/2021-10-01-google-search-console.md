---
layout: post
title: 구글에 블로그 노출시키기. (Google Search Console 이용)
description: ''
sitemap: false
hide_last_modified: false
categories:
- maint
- blog
tags: ''

---
본인 블로그를 등록 해야 구글에서 검색이 가능하다.

Google Search Console에 접속한다

[https://search.google.com/search-console/about](https://search.google.com/search-console/about "https://search.google.com/search-console/about")

SEARCH CONSOLE 버튼을 클릭한다.

시작하기 버튼을 누른다.

URL 접두어에 자신의 깃헙블로그 주소를 넣는다.

URL 접두어에 자신의 깃헙블로그 주소를 넣는다.

소유권 확인과정을 거친다.

**중요: 소유권 확인 방법은 몇가지가 있는데 한가지를 해 보고 안되면 다른 방법으로 재시도 하도록 한다. (케바케)**

html 파일을 다운받아 깃허브블로그 코드 폴더 root에 넣는다.

git repository에 push한다. 이후 바로 소유권이 확인되지 않는다.

대략 5분\~10분이상 기다려야한다.

하지만 그래도 안된다면 HTML 태그방법으로 메타 코드를 복사한다. 메타 태그를 이용한 사이트 소유권을 확인한 뒤 사이트맵을 등록해주면 된다.

_includes/head.html에 추가해준다.

한참 기다리면 소유권이 확인된다.

소유권이 확인 된 후, sitemap.xml을 입력하고 제출 버튼을 누른다.