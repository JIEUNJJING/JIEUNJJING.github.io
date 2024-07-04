---
layout: single
title: "프로그래머스 - 369게임"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120891)  

## 📌369게임
#### 📖문제 설명 :  
머쓱이는 친구들과 369게임을 하고 있습니다. 369게임은 1부터 숫자를 하나씩 대며 3, 6, 9가 들어가는 숫자는 숫자 대신 3, 6, 9의 개수만큼 박수를 치는 게임입니다. 머쓱이가 말해야하는 숫자 order가 매개변수로 주어질 때, 머쓱이가 쳐야할 박수 횟수를 return 하도록 solution 함수를 완성해보세요.

#### 입출력 예  

|order|result|
|---|---|
|3|1|
|29423|2|  


<br>

#### ✏️첫 번째 코드(오류)
```python
def solution(order):
    answer = 0
    a = list(str(order))

    for i in range(len(a)):
        if (int(a[i]) % 3 == 0):
            answer += 1

    return answer
```

#### ✏️정답 코드
```python
def solution(order):
    answer = 0
    a = list(str(order))

    for i in range(len(a)):
        if (int(a[i]) % 3 == 0) and int(a[i]) > 0:
            answer += 1

    return answer
```

<br>

#### ✨느낀점 
- 첫 번째 코드를 실행시켰을 때, 오류가 없었는데 테스트 케이스를 통과하지 못해 뭐가 잘못된건지 알 수 없었다.
  그래서 질문하기 페이지에 들어가 다른 사람들 질문을 보다보니 **입력에 0이 들어온 경우도 고려**해야한다는 말을 읽고
  !! 깨닫고.. 다시 조건을 추가해주었더니 실행이 되었다. 다음에는 이런 예외 케이스도 잘 생각해보고 실행해야겠다.
  
  
