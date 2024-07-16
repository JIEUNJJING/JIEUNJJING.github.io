---
layout: single
title: "프로그래머스 - 삼각형의 완성조건 (2)"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120868)  

## 📌삼각형의 완성조건 (2)
#### 📖문제 설명 :  
선분 세 개로 삼각형을 만들기 위해서는 다음과 같은 조건을 만족해야 합니다.

가장 긴 변의 길이는 다른 두 변의 길이의 합보다 작아야 합니다.  
삼각형의 두 변의 길이가 담긴 배열 sides이 매개변수로 주어집니다. 나머지 한 변이 될 수 있는 정수의 개수를 return하도록 solution 함수를 완성해주세요.

#### 입출력 예 

|sides|result|
|---|---|
|[1, 2]|1|
|[3, 6]|5|
|[11, 7]|13|

<br>

#### ✏️정답 코드
```python
def solution(sides):
    answer = 0
    max_num = max(sides)
    min_num = min(sides)
    sum_num = max_num + min_num

    for i in range(1, max_num + 1): # 가장 긴 변이 sides의 max값일 경우
        if i + min_num > max_num:
            answer += 1
        
    for j in range(max_num + 1, sum_num): # 가장 긴 변이 새로 들어오는 수일 경우
        answer += 1
    return answer
```

<br>

#### ✨느낀점
- 코드를 작성할 때 조건문 부분에서 좀 막혔던 거 같다. 코드를 다 작성하고 나면 다 쉬운 코드인데, 문제를 보고 풀 때 보면
  조건을 어떻게 줘야할지 생각하는 부분이 아직 조금 어려운 거 같다. 
