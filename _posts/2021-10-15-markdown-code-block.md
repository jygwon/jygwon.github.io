---
layout: post
title: 마크다운(Markdown) 코드 블록(code block)
description: ''
sitemap: false
hide_last_modified: false
categories:
- dev
tags: ''

---
마크다운에서는 **\`\`\`를** 사용해서 코드 블록을 사용할 수 있다.

    ```
    여기에 코드 넣기
    ```

또 코드 블럭 코드(\`\`\`) 시작점에 사용하는 언어를 선언하여 문법 강조가 가능하다. 아래 표가 코드블록에서 사용가능한 언어이다.

| --- | --- | --- | --- |
| 언어 | Markdown | 언어 | Markdown |
| Bash | bash | JSON | json |
| C# | cs | Java | java |
| C++ | cpp | JavaScript | javascript |
| CSS | css | PHP | php |
| Diff | diff | Perl | perl |
| HTML, XML | html | Python | python |
| HTTP | http | Ruby | ruby |
| Ini | ini | SQL | sql |

만일 python에 대한 코드 블록을 사용하고 싶다면 아래와 같이 사용하면 된다.

    ```python
    print('hello')
    ```

Line numbers for code blocks (*)

    ```{r, attr.source='.numberLines'}
    if (TRUE) {
      x <- 1:10
      x + 1
    }
    ```