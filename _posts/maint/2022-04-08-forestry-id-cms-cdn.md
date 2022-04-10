---
layout: post
title: Jekyll 기반 웹컨텐츠 관리를 웹에서 한방에 Forestry.io - 사진첨부는 덤
description: ''
sitemap: false
hide_last_modified: false
categories:
- maint
- dev
- blog
tags:
- forestry
- cms
- cdn
- 사진첨부

---
> 한줄요약: 복잡한거 싫어하면 이게 정답
>
> # Headless CMS that **commits**

**Give your editors the power of Git.  
Create, edit, and instant preview Markdown-based sites.**

forestry.io에 들어가보면 위와 같이 적혀있다.

이걸 한마디로 표현하자면 git기반 마크다운 포스트를 관리해준다는 뜻이다.

Jekyll을 사용한 깃블로그를 예로들어 설명하겠다.

위 환경에서의 포스트관리는 다음을 거친다.

1. 로컬환경에서 블로그용 폴더에 접근한다.
2. 폴더에서 atom등을 이용해 포스트용 마크다운 파일을 생성한다.(블로그 포스트 작성)
3. 로컬서버에서 테스트 해 본다.
4. 커밋 후 깃헙에 푸쉬한다.
5. 깃블로그 주소에 접속해서 확인한다.

복잡한 과정인데, 이걸 웹에서 한방에 해결해 주는게 forestry.io라고 할 수 있다.

작동원리

* forestry.io에 내 블로그의 깃헙 리포지토리를 연결해 준다.
* forestry.io가 깃헙 레포를 분석해서 포스트, 페이지 및 구성요소 별로 나열해 준다.
* forestry.io의 메뉴에서 위 구성요소를 수정가능하고 markdown은 바로보기 가능하다.
* 수정된 파일은 내 깃헙 레포지토리로 바로 업데이트된다

그러니까 forestry.io를 쓰면 그냥 웹에디터처럼 바로바로 웹상에서 수정이 가능하고 게다가 cdn기능까지 겸하고 있어 사진이나 동영상을 저장해주고 **포스트 작성시 바로 링크**해주는 기능도 해 준다. (더 이상 깃헙의 issue기능을 안써도 된다.)