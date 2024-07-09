---
layout: single
title: "프로그래머스 - k의 개수"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120887#)  

## 📌k의 개수
#### 📖문제 설명 :  
1부터 13까지의 수에서, 1은 1, 10, 11, 12, 13 이렇게 총 6번 등장합니다. 정수 i, j, k가 매개변수로 주어질 때, i부터 j까지 k가 몇 번 등장하는지 return 하도록 solution 함수를 완성해주세요.

#### 입출력 예  
|i|j|k|result|
|---|---|---|---|
|1|13|1|6|
|10|50|5|5|
|3|10|2|0|

<br>

#### ✏️틀린 코드
```python
def solution(i, j, k):
    answer = 0
    cnt = 0
    for num in range(i, j + 1):
        if str(k) in str(num):
            cnt += 1
    answer = cnt
    return answer
```
- 틀린 이유 :  
  k의 등장 횟수를 세는 문제인데, if str(k) in str(num): cnt += 1 이렇게 코드 구현을 하여 k의 등장 횟수를 카운트하게 된다. 
  이 문제는 숫자 하나하나에서 k가 몇번 등장하는지 카운트를 해야한다. (k = 1일경우, 11 -> 2번)

#### ✏️정답 코드
```python
def solution(i, j, k):
    answer = 0
    for num in range(i, j + 1):
        for i in str(num): # 숫자를 문자열로 변환 후 각 자리의 숫자 순회
            if i == str(k): # 현재 자리 숫자와 k가 같다면
                answer += 1 # 1 증가
    return answer
```

<br>

#### ✨느낀점
- 처음에 코드를 짰을 때 k가 포함된 횟수를 카운트하는 코드를 작성해 뭐가 문제인지 찾는데 조금 시간이 걸렸다.
  두 코드의 차이점인 조건문 부분을 확실하게 이해할 수 있었고, 다음엔 이런 실수를 안 하도록 해야겠다.
