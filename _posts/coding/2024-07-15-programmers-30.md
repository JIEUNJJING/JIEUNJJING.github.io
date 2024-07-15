---
layout: single
title: "프로그래머스 - 구슬을 나누는 경우의 수"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120840)  

## 📌구슬을 나누는 경우의 수
#### 📖문제 설명 :  
머쓱이는 구슬을 친구들에게 나누어주려고 합니다. 구슬은 모두 다르게 생겼습니다. 머쓱이가 갖고 있는 구슬의 개수 balls와 친구들에게 나누어 줄 구슬 개수 share이 매개변수로 주어질 때, balls개의 구슬 중 share개의 구슬을 고르는 가능한 모든 경우의 수를 return 하는 solution 함수를 완성해주세요.

#### 입출력 예  

|balls|share|result|
|---|---|---|
|3|2|3|
|5|3|10|

<br>

#### ✏️정답 코드
```python
from math import factorial as fac
def solution(balls, share):
    answer = 0

    d = fac(balls)
    n1 = fac(balls - share)
    n2 = fac(share)

    answer = d //(n1 * n2)
    return answer
```

<br>

#### ✨코드 설명
- factorial 함수를 사용하면 쉽게 문제를 풀 수 있다. 문제에 주어진 힌트를 보고 식을 작성하였다.
  factorial 함수에 대해 잘 몰라서 다른 사람들의 코드를 보고 참고하여 문제 풀이를 하였다. 
