---
layout: single
title: "프로그래머스 - 간단한 식 계산하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181865)  

## 📌간단한 식 계산하기
#### 📖문제 설명 :  
문자열 binomial이 매개변수로 주어집니다. binomial은 "a op b" 형태의 이항식이고 a와 b는 음이 아닌 정수, op는 '+', '-', '*' 중 하나입니다. 주어진 식을 계산한 정수를 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예  

|binomial|result|
|---|---|
|"43 + 12"|55|
|"0 - 7777"|-7777|
|"40000 * 40000"|1600000000|

<br>

#### ✏️내 코드
```python
def solution(binomial):
    answer = 0
    b = binomial.split(" ")
    if b [1] == "+":
        answer = int(b[0]) + int(b[2])
    elif b [1] == "-":
        answer = int(b[0]) - int(b[2])
    else:
        answer = int(b[0]) * int(b[2])

    return answer
```

#### ✏️다른사람 코드
```python
def solution(binomial):
    answer = 0
    answer = eval(binomial)

    return answer
```

<br>

#### ✨느낀점 
- 나는 split()함수를 사용해 공백 기준으로 나누어 준 후, 비교해 연산된 값을 answer에 넣어주었는데, 다른 사람들의 풀이를 보니
  eval()이라는 함수를 사용하면 한줄로도 이 문제를 해결할 수 있다는 것을 알게되었다. **solution = eval**이렇게 주어 푼 사람도 있었다.
  
