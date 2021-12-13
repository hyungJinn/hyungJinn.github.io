---
title: "Algorithm: 백트래킹(Backtracking)"

categories:
  - Algorithm
tags:
  - Backtracking

search: true
comments: true
---

> Algorithm

### 접근

해를 찾는 도중 해가 아니어서 막히면, 되돌아가서 다시 해를 찾아가는 기법.

해를 찾는 도중에 지금의 경로가 해가 될 것 같지 않으면 그 경로를 더 이상 가지 않고 되돌아간다.
코딩에서 반복문의 횟수를 줄일 수 있으므로 효울적이다(가지치기).
불필요한 부분을 쳐내고 최대한 올바른 쪽으로 간다는 의미.

모든 경우의 수를 전부 고려하는 알고리즘
상태 공간을 트리로 나타낼 수 있을 때 적합한 방식이다.
일종의 트리 탐색 알고리즘이라고 봐도 된다.
방식에 따라서
깊이 우선 탐색(Depth First Search, DFS)
너비 우선 탐색(Breadth First Search, BFS)
최선 우선 탐색(Best First Search / Heuristic Search)

백트래킹 알고리즘은 노드의 유망성 점검 후, 유망하지 않으면 그 노드의 부모로 되돌아간 후 다른 자식 노드를 검색하는 알고리즘이다.

### 백트래킹 기법의 유망성 판다

어떤 노드가 해가 될 만한지 판단한 후에 유망하지 않다고 결정되면 그 노드의 이전 노드로 돌아가(backtracking) 다른 자식 노드로 간다.

해가 될 가능성이 있으면 = 유망하다(promising)
유망하지 않은 노드에 가지 않는 것 = 가지치기(pruning)

[백준 9663번: N-Queen](https://www.acmicpc.net/problem/9663)
