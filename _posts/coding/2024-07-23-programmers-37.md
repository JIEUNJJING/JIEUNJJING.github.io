---
layout: single
title: "프로그래머스 - 종이 자르기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120922)  

## 📌종이 자르기
#### 📖문제 설명 :  
머쓱이는 큰 종이를 1 x 1 크기로 자르려고 합니다. 예를 들어 2 x 2 크기의 종이를 1 x 1 크기로 자르려면 최소 가위질 세 번이 필요합니다.

![스크린샷 2024-07-24 083511](https://github.com/user-attachments/assets/24b66b8c-a172-406e-996e-6e035f7bcc80)
Format: ![Alt Text](url)

정수 M, N이 매개변수로 주어질 때, M x N 크기의 종이를 최소로 가위질 해야하는 횟수를 return 하도록 solution 함수를 완성해보세요.
#### 입출력 예 

|M|N|result|
|---|---|---|
|2|2|3|
|2|5|9|
|1|1|0|

<br>

#### ✏️오류 코드 
```python
def solution(M, N):
    answer = ''
    cnt = 0

    if M <= 2:
        cnt += M - 1
        if N <= 2:
            cnt += (N - 1) * 2
        else:
            cnt += (N-1) * 2
    else:
        cnt += (M-1) * 2
        if N <= 2:
            cnt += (N - 1) * 2
        else:
            cnt += (N-1) * 2

    answer = cnt
    return answer
```

#### ✏️정답 코드
```python
def solution(M, N):
    answer = 0
    
    answer = (M * N) - 1
    return answer
```

<br>

#### ✨코드설명
- 코드를 작성할 때 너무 어렵게 문제를 풀려고 했던 거 같다. 계속 실행 오류가 나서 구글링을 해봤더니,
  저렇게 쉽게 코드를 작성한 사람이 있었다. 문제를 너무 어렵게 풀려고 하지 말아야겠다. 쉽게 생각하는 것도 하나의 코딩 기술인 거 같다..!
