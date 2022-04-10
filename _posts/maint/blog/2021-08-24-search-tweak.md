---
layout: post
title: 깃블로그 search이 정상적으로 동작하지 않을 때
description: >
sitemap: false
hide_last_modified: false
categories:
  - maint
  - blog
tags: search 검색
---

  한줄요약: wholeWords를 매칭하지 않도록 하는게 핵심
  
깃블로그 search 검색값이 올바로 나오지 않는 경우는 아래의 파일에서
코드블럭과 같이 적혀 있는지 확인한다.


1. 최소 검색글자를 지정해준다.

2. 'wholeWords' : false,를 적어주어 단어의 일부만으로도 검색결과가 나오도록 한다.

search.html
~~~html
<form action="{{ page.url | relative_url }}">
  <!-- <div class="tipue_search_left"><img src="{{ "/assets/tipuesearch/search.png" | relative_url }}" class="tipue_search_icon"></div> -->
  <div class="tipue_search_left"><img src="{{ "" | relative_url }}" class="tipue_search_icon"></div>
  <div class="tipue_search_right"><input type="text" name="q" id="tipue_search_input" pattern=".{3,}" title="At least 3 characters" required></div>
  <div style="clear: both;"></div>
</form>

<div id="tipue_search_content"></div>

<script>
$(document).ready(function() {
  $('#tipue_search_input').tipuesearch({
    'wholeWords' : false,
    'showTime'   : false,
    'minimumLength' : 2
  });
});
</script>
~~~
