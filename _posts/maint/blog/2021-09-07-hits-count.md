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

![](/uploads/capture.PNG)

***

## 사이트 방문자 조회

내 사이트 방문수를 알고 싶다면 사이트 방문시 무조건 한번은 불러오는 사이드바에 Hits를 달아준다.

_includes/body/sidebar-sticky.html에 복사한 것을 붙여 넣어주면 된다.

***

## 게시물 읽은회수 조회

게시물에는 정적 페이지가 빌드 될 때마다 자동으로 hits에서 만든 배지를 삽입하도록 해준다. Jekyll 기준 게시글의 레이아웃을 지정하는 파일은 _include/post.html 이다.

아까 사용했던 코드 form을 넣어준다.

```html
<div style="text-align:right; text-align: center">
    <a href="https://hits.seeyoufarm.com/{{ site.url | remove_first: 'https: //' | remove_first: 'http://' }}{{ page.url }}" target="_blank">
        <img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https://
{{ site.url | remove_first: 'https://' | remove_first: 'http://' }}{{ page.url }}&count_bg=%23293786&title_bg=%23555555&icon=bilibili.svg&icon_color=%23E7E7
E7&title=.&edge_flat=false" /> </a>
</div>
```