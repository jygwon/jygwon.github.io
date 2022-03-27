---
layout: post
title: 마크다운 게시물에 유튜브 영상 넣기
description: >
sitemap: false
hide_last_modified: false
categories:
  - dev
---

아래 경로의 파일에 코드블럭을 넣어준다.
_includes > youtubePlayer.html
~~~
<style>
    .embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; }
    .embed-container iframe,
    .embed-container object,
    .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }
</style>

<div class="embed-container" >
    <iframe src="https://www.youtube.com/embed/{{ include.id }}" frameborder="0" allowfullscreen="" onclick="ga('send', 'event', 'post', 'click', 'youtubePlayer');">
    </iframe>
</div>
~~~


원하는 마크다운 게시물 위치에 원하는 유튜브 영상 id와 함께 아래 코드를 입력하면 됩니다.
~~~
<% include youtubePlayer.html id="yypCzKVyiKs" %>
꺽쇠를 {}로 바꾸세요.
~~~

{% include youtubePlayer.html id="yypCzKVyiKs" %}
