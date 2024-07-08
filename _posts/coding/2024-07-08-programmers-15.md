---
layout: single
title: "프로그래머스 - 문자열이 몇 번 등장하는지 세기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181871)  

## 📌문자열이 몇 번 등장하는지 세기
#### 📖문제 설명 :  
문자열 myString과 pat이 주어집니다. myString에서 pat이 등장하는 횟수를 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예  

|num_list|n|result|
|---|---|---|
|"banana"|"ana"|2|
|"aaaa"|"aa"|3|

<br>

#### ✏️틀린 코드
```python
def solution(myString, pat):
    answer = 0
    start = 0

    for i in range(len(myString)):
        if myString[i:] == pat:
            print(myString[i:])
            answer +=1
    return answer
```

#### ✏️내 코드
```python
def solution(myString, pat):
    answer = 0

    for i in range(len(myString)):
        if myString[i:len(pat) + i] == pat: #i번째부터 len(pat) + i까지 비교(pat길이만큼 비교해줘야함)
            answer +=1
    return answer
```

<br>

#### ✨구현 방법 
- len(myString)까지 반복문을 돌며, i번째부터 len(pat) + i까지 비교했을 때 pat과 같다면 answer에 1을 더해준다.
  len(pat) + i까지 비교해주는 이유는 pat과 같아야하기 때문이다. 
  
#### ✨느낀점
- 처음에 코드를 짰을 떄, 조건문을 if myString[i:] == pat:이렇게 줘도 된다고 생각했는데, 이렇게 해버리면 i번째 인덱스부터
  끝까지의 부분 문자열의 동일해야만 조건이 참이 되기 때문에 문제가 발생하는 것을 알게되었습니다.  
  
  
