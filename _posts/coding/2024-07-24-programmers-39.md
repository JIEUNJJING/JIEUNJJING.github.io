---
layout: single
title: "프로그래머스 - 캐릭터의 좌표"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120861)  

## 📌캐릭터의 좌표
#### 📖문제 설명 :  
![image](https://github.com/user-attachments/assets/c8c13894-b48a-4cf9-a0c0-9a00934d1711)

#### 📖제한 사항 :  
![image](https://github.com/user-attachments/assets/cf9cf786-9bef-4547-82d3-e5fe8f7d830a)

#### 📖입출력 예 : 
|keyinput|board|result|
|---|---|---|
|["left", "right", "up", "right", "right"]|[11, 11]|[2, 1]|
|["down", "down", "down", "down", "down"]|[7, 9]|[0, -4]|

#### 📖입출력 예 설명 : 
![image](https://github.com/user-attachments/assets/299f639e-14da-49ef-b384-b31ba24db44f)<br>

#### ✏️정답 코드
```python
def solution(keyinput, board):
    answer = [0, 0]
    a = board[0] // 2
    b = board[1] // 2

    for i in keyinput:
        if i == 'up' and answer[1] < b:
            answer[1] += 1
        elif i == 'down' and answer[1] > -b:
            answer[1] -= 1
        elif i == 'right' and answer[0] < a:
            answer[0] += 1
        elif i == 'left' and answer[0] > -a:
            answer[0] -= 1

    return answer
```

<br>

#### ✨코드설명
- board의 크기를 벗어나면 안되므로, 조건문을 줄 때 같이 적어줘야한다. 'down'일 때는 -b보다 클 때 answer[1]에 -1을 더해줘야하고,
  'left'일 때는 -a보다 클 때 answer[0]에 -1을 더해줘야하는데 처음 코드를 작성할 때 조건을 작을 때 더해준다는 조건을 주어 자꾸 오류가 났었다.
  다음부턴 실수하지 않도록 문제는 물론 조건문을 줄 때 한 번 더 생각하고 코드를 작성해야겠다. 
  
