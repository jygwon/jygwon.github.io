---
layout: post
title: 검색 엔진 최적화 (SEO)
description: 
sitemap: false
hide_last_modified: false
categories:
- maint
- blog
tags: 

---
# 검색엔진최적화

검색엔진최적화는 검색엔진이 이해하기 쉽도록 홈페이지 구조를 설정하여 포털 사이트 상위에 노출시키는 작업이다.

jekyll으로 제작된 깃허브 블로그에 SEO 작업을 진행한다.

## Sitemap

* 웹 크롤링 로봇이 이용할 수 있는 웹사이트의 접근 가능한 페이지의 목록
* 사이트맵을 등록하면 구글에서 주기적으로 크롤링을 한 뒤 관련 검색어로 검색 시 해당 사이트가 노출이 된다.
* sitemap.xml 파일을 사용하면 사이트 구조를 구글, 네이버, 다음 등 검색엔진에 손 쉽게 제출할 수 있다.
* 검색엔진에 크롤링해야하는 URL을 알려줌으로써 색인을 생성하는 방법을 제안한다.

그럼 이제 Sitemap.xml을 생성해본다.

아래 내용으로 sitemap.xml 파일을 만들고 root 경로에 넣어준다.

    ---
    layout: null
    ---
    <?xml version="1.0" encoding="UTF-8"?>
    <urlset xmlns:xsi="<http://www.w3.org/2001/XMLSchema-instance>" xsi:schemaLocation="<http://www.sitemaps.org/schemas/sitemap/0.9> <http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd>" xmlns="<http://www.sitemaps.org/schemas/sitemap/0.9>">
      {% for post in site.posts %}
        <url>
          <loc>{{ site.url }}{{ post.url }}</loc>
          {% if post.lastmod == null %}
            <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
          {% else %}
            <lastmod>{{ post.lastmod | date_to_xmlschema }}</lastmod>
          {% endif %}
    
          {% if post.sitemap.changefreq == null %}
            <changefreq>weekly</changefreq>
          {% else %}
            <changefreq>{{ post.sitemap.changefreq }}</changefreq>
          {% endif %}
    
          {% if post.sitemap.priority == null %}
              <priority>1.0</priority>
          {% else %}
            <priority>{{ post.sitemap.priority }}</priority>
          {% endif %}
    
        </url>
      {% endfor %}
    </urlset>
    

* 해당 파일을 커밋, 푸쉬 한다.
* 블로그 주소/sitemap.xml 에 들어가서 제대로 사이트맵이 등록되었는지 확인해 본다.
* 홈페이지의 모든글의 정보를 담고있는 사이트맵이 출력되는 것을 알 수 있다. 추후에 블로그 포스팅을 푸쉬 하면 jekyll이 빌드하면서 사이트맵도 자동으로 갱신된다.
* Gemfile파일에 gem ‘jekyll-sitemap’이 있는것을 확인해보고 있다면 자동으로 갱신된다. (참고로 /sitemap.xml을 실행했을 때 제대로 안 나오는 경우가 있는데, 주소 링크에 특수문자가 들어간 경우이다. 깃허브 블로그의 경우 포스팅 파일명으로 링크가 생성되므로 포스팅 파일명은 특수문자 및 한글 사용을 안 하도록 한다.)

## RSS

* RSS(Rich Site Summary)란 뉴스나 블로그 사이트에서 주로 사용하는 콘텐츠 표현 방식이며, 웹 사이트 관리자는 RSS 형식으로 웹 사이트 내용을 보여 준다.
* RSS피드는 정기적으로 업데이트 되는 웹 콘텐츠를 전달해 주는 형태이며, 글의 전체 혹은 요약된 정보와 작성자 등의 정보가 포함되어 있다. 즉 블로그의 글을 작성하면 RSS피드에도 전달이 되고, 구글, 네이버, 다음 등을 통해 글을 검색하면, 검색 엔진은 블로그의 RSS피드로부터 글을 받게 되어 해당 블로그로 들어오게 된다.

그럼 이제 RSS feed.xml을 생성한다.

sitemap.xml과 동일하게 root 경로에 만들어주고 아래 코드를 넣어준다.

    ---
    layout: null
    ---
    <?xml version="1.0" encoding="UTF-8"?>
    <rss version="2.0" xmlns:atom="<http://www.w3.org/2005/Atom>">
      <channel>
        <title>{{ site.title | xml_escape }}</title>
        <description>{{ site.description | xml_escape }}</description>
        <link>{{ site.url }}{{ site.baseurl }}/</link>
        <atom:link href="{{ "/feed.xml" | prepend: site.baseurl | prepend: site.url }}" rel="self" type="application/rss+xml"/>
        <pubDate>{{ site.time | date_to_rfc822 }}</pubDate>
        <lastBuildDate>{{ site.time | date_to_rfc822 }}</lastBuildDate>
        <generator>Jekyll v{{ jekyll.version }}</generator>
        {% for post in site.posts limit:30 %}
          <item>
            <title>{{ post.title | xml_escape }}</title>
            <description>{{ post.content | xml_escape }}</description>
            <pubDate>{{ post.date | date_to_rfc822 }}</pubDate>
            <link>{{ post.url | prepend: site.baseurl | prepend: site.url }}</link>
            <guid isPermaLink="true">{{ post.url | prepend: site.baseurl | prepend: site.url }}</guid>
            {% for tag in post.tags %}
            <category>{{ tag | xml_escape }}</category>
            {% endfor %}
            {% for cat in post.categories %}
            <category>{{ cat | xml_escape }}</category>
            {% endfor %}
          </item>
        {% endfor %}
      </channel>
    </rss>
    

해당 파일을 커밋, 푸쉬 하고 블로그 주소/feed.xml 에 제대로 등록되었는지 확인해 본다.

## robots

robots.txt 또는 robots.xml은 로봇 배제 표준을 따르는 일반 텍스트 파일이다.

쉽게 표현하면 검색 엔진이 해당 사이트의 콘텐츠를 가져가는것을 허락하는 설정과 가져가면 안되는 설정을 하는 부분이라고 보면 된다.

위와 동일하게 root 경로에 위치한다.

robots.xml을 생성한다.

아래와 같이 입력한다.

    User-agent: *
    Allow: /
    
    Sitemap: <http://username.github.io/sitemap.xml>
    

User-agent는 허용할 검색엔진 명을 넣게 된다.

따로 설정하지 않으면(*) 모든 검색엔진을 허용하게 된다.

Sitemap은 본인 블로그 사이트맵 주소를 넣어 주면 된다.