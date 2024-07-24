---
layout: single
title: "프로그래머스 - 직사각형 넓이 구하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120860)  

## 📌직사각형 넓이 구하기
#### 📖문제 설명 :  
![image](https://github.com/user-attachments/assets/af447a7f-2153-4b34-b10c-08e688263e9d)

![image](https://github.com/user-attachments/assets/f7af2dd0-ee9b-4725-b67b-b0269f913b21)

![image](https://github.com/user-attachments/assets/be317654-46e4-41fc-ac95-ab1a8c8c1333)

<br>

#### ✏️정답 코드
```python
def solution(dots):
    answer = 0

    x = max(dots)[0] - min(dots)[0]
    y = max(dots)[1] - min(dots)[1]

    answer = x * y
    return answer
```

<br>

#### ✨코드설명
- x, y값을 구할 때, max(dots)[0] - min(dots)[0] 이렇게 적어준 이유는 max(dots)이 코드가 [1,1]와 같은 형태를 나타내기 때문에
  max(dots)[0] 이렇게 해준다면 0번째 자리의 가장 큰값에서 작은 값을 빼주어 x(가로)값을 구할 수 있다.
  y도 x와 마찬가지로 코드를 작성해 구해준 후, 곱해주면 직사각형 넓이를 구할 수 있다.
  
