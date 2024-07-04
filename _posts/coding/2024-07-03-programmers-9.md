---
layout: single
title: "프로그래머스 - 제곱수 판별하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120909)  

## 📌제곱수 판별하기
#### 📖문제 설명 :  
어떤 자연수를 제곱했을 때 나오는 정수를 제곱수라고 합니다. 정수 n이 매개변수로 주어질 때, n이 제곱수라면 1을 아니라면 2를 return하도록 solution 함수를 완성해주세요.

#### 입출력 예  

|n|result|
|---|---|
|144|1|
|976|2|  


<br>

#### ✏️코드
```python
import math
def solution(n):
    answer = 0
    if n % math.sqrt(n) == 0: # 제곱수구함
        answer = 1
    else:
        answer = 2

    return answer
```

<br>

#### ✨느낀점 
- 제곱수를 어떻게 구하면 좋을지 너무 막막했는데 sqrt() 함수를 사용하면 된다는 힌트를 얻었다.
  먼저, math모듈을 불러와 math.sqrt(n)을 해주면 n의 제곱근을 계산할 수 있다.
  그러고나서 n % math.sqrt(n)를 해주었을 때, 나머지가 0일 경우 제곱수임을 의미하고, 0이 아니라면 제곱수가 아님을 뜻한다.
  
  
