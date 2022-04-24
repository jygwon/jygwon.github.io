---
layout: post
title: 코딩테스트를 위한 알고리즘 공부 순서
description: ''
sitemap: false
hide_last_modified: false
categories:
- algo
tags: ''

---
한줄요약: 코딩 테스트를 본다면 반띵을 하면 통과다. 그러므로 반띵에 맞는 공부를 하자.

주변에 보면 코딩테스트 공부 시작했다가 얼마 안가 포기했다는 이야기를 하는 친구들이 있다. 그 중 일부에게 이유를 물어보았는데, 그 대답은 "너무 어렵고 공부할게 많다" 라는 것이다. 그래서 조금 더 깊이 물어보게 되었는데, 알아낸 것은 이 친구는 코딩테스트가 아니라 알고리즘 공부를 하고 있었다는 것.

코딩테스트란 무엇인가? 시험치는 사람이 코딩에 대한 기본기가 있는지 필터링하는 도구이다. 그러므로 가장 많이 사용되고 기본기가 되는 내용을 알고 있는가를 검증한다. 무슨 석박사급의 알고리즘 이해도를 요구하는게 아니다.

헌데, 코딩테스트를 위한 알고리즘을 공부하다가 점점 산으로 가서 알고리즘을 위한 알고리즘을 공부하는 친구들을 보게된다. 물론 알고리즘이 재미있어서 하는 것은 이해하겠는데... 취업은 해야될 것 아닌가...

그래서 코딩테스트에서 요구하는 알고리즘의 범위가 어디인지 좀 알아보도록 하자.

1. 배열조작, 정렬

   요건 정말 기본중에 기본이라 아예 안물어보고 넘어가는 경우가 대부분이다. 헌데, 재수없게 나올 수 있으므로 일단 보고가는게 맞다.

   배열 또는 문자열 조작 같은 경우는 문제 풀이 중 허다하게 써야 하므로 자연스럽게 몸에 배게 될 것이다. 헌데 정렬의 경우는 그냥 내부함수 써서 처리하기 때문에 잘 모르고 지나가는 경우가 많다. 그런데 재수없게 문제에 머지소트 구현하라고 나오면 공부 좀 한 사람한테는 거져주는 점수지만 한번도 안해봤다면 틀릴 수 밖에 없다. 그러니 개념과 잘 짜여진 샘플코드를 몇번 봐서 떠올리면서 코드를 구현할 정도는 되어야 한다.
2. 리스트, 해쉬테이블, 맵, 힙

   이것도 너무 기본이라 안다고 생각하고 안물어보는 내용인데 재수없으면 나온다.

   ADT주고 링크드리스트 구현해 봐라 요런문제 나오면 공부한 사람은 거저먹는 점수지만 안한 사람은 감도 안올거다. 그래서 정리는 하고 넘어가야 한다.
3. 완전탐색 - bfs, dfs, 순열 조합

   [https://www.acmicpc.net/workbook/view/446](https://www.acmicpc.net/workbook/view/446 "https://www.acmicpc.net/workbook/view/446") 완탐

   [https://www.acmicpc.net/workbook/view/593](https://www.acmicpc.net/workbook/view/593 "https://www.acmicpc.net/workbook/view/593") 순열조합

   위 기본기랑 자료구조 조금 공부하고 알고리즘 중 이거 딱 하나만 해도 재수가 좋으면 반타작해서 입갤 가능하다.
4. 그리디

   [https://it-college-diary.tistory.com/entry/21-Greedy-Algorithm%ED%83%90%EC%9A%95%EB%B2%95-%EC%9A%95%EC%8B%AC%EC%9F%81%EC%9D%B4-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EA%B0%9C%EB%85%90](https://it-college-diary.tistory.com/entry/21-Greedy-Algorithm%ED%83%90%EC%9A%95%EB%B2%95-%EC%9A%95%EC%8B%AC%EC%9F%81%EC%9D%B4-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EA%B0%9C%EB%85%90 "https://it-college-diary.tistory.com/entry/21-Greedy-Algorithm%ED%83%90%EC%9A%95%EB%B2%95-%EC%9A%95%EC%8B%AC%EC%9F%81%EC%9D%B4-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EA%B0%9C%EB%85%90") 문제집

   dp의 일부로 보는 사람도 있으나, 그래도 별도의 알고리즘으로 보고 공부하는 것이 좋다. 문제에서 그리디의 냄새를 맡아내는 좋은 촉을 키우는 것으로 시작해 본다. 보통 완탐으로 가다가 시간초과나 오버플로 날 것 같은 냄새가 솔솔 나면 그리디로 가게 된다.
5. 기본dp

   [https://stonejjun.tistory.com/24](https://it-college-diary.tistory.com/entry/21-Greedy-Algorithm%ED%83%90%EC%9A%95%EB%B2%95-%EC%9A%95%EC%8B%AC%EC%9F%81%EC%9D%B4-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EA%B0%9C%EB%85%90 "https://it-college-diary.tistory.com/entry/21-Greedy-Algorithm%ED%83%90%EC%9A%95%EB%B2%95-%EC%9A%95%EC%8B%AC%EC%9F%81%EC%9D%B4-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EA%B0%9C%EB%85%90") 문제집

   dp는 알고리즘의 꽃이다. 그래서 공부할게 많다. 그래서 우리는 기본 dp만 한다. 코테에서는 다양한 수준의 dp가 나온다. 초급 수준 dp는 점수 먹으라고 주는 것이기 때문에 여기서 틀리면 커트라인을 통과할 수 없다. 그래서 기본 dp는 공부하고 넘어가야 한다.

   일단 문제를 읽으면 dp의 냄새가 나는데? 라는 생각을 할 수 있는 수준까지 올리는 것을 1차 목표로 한다.

공부법

* 3가지 알고리즘에 해당하는 초급문제를 각 50개 풀어본다.
* 감을 잡았으면 실전문제나 중고급 기출문제집을 풀어본다.
* 어느정도 감을 잡고 모의 코테 점수가 반타작 근처에서 왔다갔다 한다면 안정권을 노리기 위해 다른 알고리즘을 공부한다.

공부해야 할 추가 알고리즘.

* 그래프
* 중고급dp
* 문자열
* 비트연산