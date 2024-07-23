---
layout: single
title: "프로그래머스 - 1로 만들기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181880)  

## 📌1로 만들
#### 📖문제 설명 :  
정수가 있을 때, 짝수라면 반으로 나누고, 홀수라면 1을 뺀 뒤 반으로 나누면, 마지막엔 1이 됩니다. 예를 들어 10이 있다면 다음과 같은 과정으로 1이 됩니다.

10 / 2 = 5
(5 - 1) / 2 = 2
2 / 2 = 1
위와 같이 3번의 나누기 연산으로 1이 되었습니다.

정수들이 담긴 리스트 num_list가 주어질 때, num_list의 모든 원소를 1로 만들기 위해서 필요한 나누기 연산의 횟수를 return하도록 solution 함수를 완성해주세요.

#### 입출력 예 

|num_list|result|
|---|---|
|[12, 4, 15, 1, 14]|11|

<br>

#### ✏️정답 코드
```python
def solution(num_list):
    answer = 0
    cnt = 0

    for i in num_list:
        while(i != 1):
            if i % 2 == 0:
                i = i // 2
                cnt += 1
            else:
                i = (i - 1) / 2
                cnt += 1

        answer = cnt
    return answer
```

<br>

#### ✨코드설명
- 반복문을 사용해 num_list안 원소들을 하나씩 방문하며 그 원소가 1이 될때까지 나누기를 반복하는 코드를 작성했다.
  한번 나누기 연산을 실행할 때마다 횟수를 카운트해주기위해 cnt라는 변수를 주어 횟수를 카운트하였다. 
  처음에 while문 조건을 i != 0으로 해서 계속 틀리는 실수를 했다. 문제를 풀 때, 문제 설명을 자세히 잘 읽어야겠다는 생각이 들었다.
  
