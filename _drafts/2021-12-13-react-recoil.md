---
title: "React: Recoil"

categories:
  - React
tags:
  - Recoil

search: true
comments: true
---

> BOJ

[Recoil](https://recoiljs.org/)

### 설명

Recoil은 React JS에서 state management를 위한 해결책이다.

React에서 state management는 정말 중요한 개념이다.

어플리케이션의 state에 기반하여 바꾼다?

global state는 어플리케이션의 특정 value에 접근해야 할 때 쓴다.
어플리케이션 전체에서 공유되는 state
예를 들면, 유저의 로그인 여부.
isDark: App -> Router -> Coin -> Chart
위의 방식은 좋지 않다

Header -> (isDark) <- Chart
App -> (isDark)
위와 같은 버블 형식이 좋다?
하나의 방울 안에서 isDark Value를 보관하는 것
Chart나 App과 같이 그 value가 필요한 componenet만 그 value를 가지게 만들어 준다.

component를 어떻게 atomd의 value로 연결하는지
어떻게 atom의 value를 수정하는지

atom을 연결하고, value를 가져오고, 수정한는 법

많은 component들이 많은 props를 가지고 있는 큰 규모의 앱에서 Traveling Prop이 일어나게 되면, 이 prop이 뭘 하고 있고 왜 이 컴포넌트가 이 prop을 필요로 하는 건지 헷갈리게 된다.
atoms는 우리 앱의 상태의 파편들이고 이걸로 2가지를 할 수 있다.

atoms의 값을 관찰할 수 있다.
atoms의 값을 수정할 수 있다.



### Correct Solution

```python
import sys
from collections import deque
input = sys.stdin.readline

A, B, C = map(int, input().split())

def pour(x, y):
    if not visit[x][y]:
        visit[x][y] = True
        q.append([x, y])


def bfs():
    # bfs 시작!
    q.append([0, 0])
    visit[0][0] = True

    while q:
        x, y = q.popleft()
        z = C - x - y
        if x == 0:
            ans.append(z)

        # x -> y
        water = min(x, B - y)
        pour(x - water, y + water)

        # x -> z
        water = min(x, C - z)
        pour(x - water, y)

        # y -> x
        water = min(y, A - x)
        pour(x + water, y- water)

        # y -> z
        water = min(y, C - z)
        pour(x, y - water)

        # z -> x
        water = min(z, A - x)
        pour(x + water, y)

        # z -> y
        water = min(z, B - y)
        pour(x, y + water)


q = deque()
ans = []

visit = [[False] * (B + 1) for _ in range(A + 1)]
bfs()

ans.sort()
print(' '.join(map(str, ans)))

```

### 참고 사이트

[ChanBLOG]](https://chanhuiseok.github.io/posts/baek-1/)
