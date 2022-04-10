---
layout: post
title: 깃블로그 마크다운 포스팅 글에 이미지 삽입하기
description: 
sitemap: false
hide_last_modified: false
categories:
- maint
- blog
tags: github blog pat token

---
한줄요약: 리포지토리내 issue생성시 githubusercontent.com이라는 CDN에 업로드 되는 파일을 이용하는 꼼수. (실제 이슈를 생성하지 말고 업로드된 파일만 링크하자.)

MarkDown에 이미지 간편 삽입 방법

1. 깃헙에 로긴한다.
2. Git Hub의 저장소에 들어가 'Issues' 탭을 클릭한다.
3. 'New issue'를 클릭한다.
4. 아래 빈칸으로 원하는 이미지를 drag한다.
   이렇게 하면 githubusercontent으로 자동으로 이미지가 업로드 되며
   해당 파일의 url이 생성되는데, 이 url을 사용하면 이미지를 사용할 수 있다.
5. MarkDown에 이미지 삽입 위 방법대로만 수행하면 불편하지않고 쉽게 삽입할 수 있습니다.
6. 이렇게 될 경우 cdn이 막혀버리면 내가 업로드한 그림파일이 다 사라지는 위험이 있을 수 있다.
7. 간단한건 이렇게 관리하고 [forestry.io]({% post_url 2021-08-20-what-ruby%})와 같은 cms를 이용하는게 좋다.

![800px-The Matrix glmatrix 2](https://user-images.githubusercontent.com/101961604/162370322-bc3fc791-75f6-4f96-ad62-3dc5fc686db3.png)

    ![800px-The Matrix glmatrix 2](https://user-images.githubusercontent.com/101961604/162370322-bc3fc791-75f6-4f96-ad62-3dc5fc686db3.png)