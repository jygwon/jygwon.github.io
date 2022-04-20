---
layout: post
title: 방문자 조회수 카운트 달기
description: 
sitemap: false
hide_last_modified: false
categories:
- maint
- blog
tags: 

---
깃헙블로그의 경우 Jekyll이나 Hugo와 같은 정적 사이트 생성기로 제작되었기 때문에 블로그 방문자와의 상호작용을 기록할 수 없다.

자체적인 백엔드가 없기 때문에 서드파티 서비스를 이용해야 한다. 대표적으로 댓글기능의 경우는 보통 Disqus나 utterances를 이용해서 구현하고, 방문 기록 분석은 구글 애널리틱스를 이용한다.

하지만 내 글의 조회수를 보여주고 싶다면 어떻게 해야할까?

## Hits를 이용하자!

Hits는 본래 깃헙 레파지토리 방문자 수를 세기 위해 만들어졌다.

[HITS](https://hits.seeyoufarm.com/)

위 링크에 들어가서 커스텀해준다.

그리고 아래로 조금만 내리면 아래와 같은 화면을 볼 수 있다.

이중 HTML LINK를 복사한다.

각 게시물에 Hits를 보여주는 것도 좋지만 그전에 먼저 전체적인 내 페이지 조회수를 알고 싶다.

그래서 페이지에서 무조건 한번은 불러오는 사이드바에 Hits를 달아본다.

![스크린샷 2021-12-20 오후 8.53.58.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d8753305-5045-4beb-aaa4-4fee17458d99/스크린샷_2021-12-20_오후_8.53.58.png)

_includes/body/sidebar-sticky.html에 복사한 것을 붙여 넣어주면 된다.

원하는 위치에 옮겨본다.

***

## 3.10.2 게시물에 넣기

배지 자동 생성 레이아웃 설정

하지만 매번 글을 쓸 때마다 이렇게 배지를 다는 것은 번거롭다. 오타를 내서 URL의 일관성이 떨어질 문제도 있다.

때문에 정적 페이지가 빌드 될 때마다 자동으로 배지를 삽입하도록 해본다. Jekyll 기준 게시글의 레이아웃을 지정하는 파일은 _include/post.html 이다.

![스크린샷 2021-12-20 오후 8.54.52.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/34dfb234-a1e4-412b-95bb-81f833efda5b/스크린샷_2021-12-20_오후_8.54.52.png)

아까 사용했던 코드 form을 사용한다.

```html
<div style="text-align: center;">
    <a href="http://hits.dwyl.com/{{ site.url | remove_first: 'https://' | r
emove_first: 'http://' }}{{ page.url }}" target="_blank">
        <img src="http://hits.dwyl.com/{{ site.url | remove_first: 'https://' | r
emove_first: 'http://' }}{{ page.url }}.svg" /> </a>
</div>
```

```html
<div style="text-align:right; text-align: center">
    <a href="https://hits.seeyoufarm.com/{{ site.url | remove_first: 'https: //' | remove_first: 'http://' }}{{ page.url }}" target="_blank">
        <img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https://
{{ site.url | remove_first: 'https://' | remove_first: 'http://' }}{{ page.url }}&count_bg=%23293786&title_bg=%23555555&icon=bilibili.svg&icon_color=%23E7E7
E7&title=.&edge_flat=false" /> </a>
</div>
```