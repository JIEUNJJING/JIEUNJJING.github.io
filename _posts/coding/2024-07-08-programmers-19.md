---
layout: single
title: "프로그래머스 - 진료순서 정하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120835)  

## 📌진료순서 정하기
#### 📖문제 설명 :  
외과의사 머쓱이는 응급실에 온 환자의 응급도를 기준으로 진료 순서를 정하려고 합니다. 정수 배열 emergency가 매개변수로 주어질 때 응급도가 높은 순서대로 진료 순서를 정한 배열을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예  
|emergency|result|
|---|---|
|[3, 76, 24]|[3, 1, 2]|
|[1, 2, 3, 4, 5, 6, 7]|[7, 6, 5, 4, 3, 2, 1]|
|[30, 10, 23, 6, 100]|[2, 4, 3, 5, 1]|

<br>

#### ✏️내 코드
```python
def solution(emergency):
    answer = []
    
    for i in emergency:
        seq = 1 # 1로 초기화
        for j in emergency:
            if i < j:
                seq += 1
        answer.append(seq)
    return answer

```

<br>

#### ✨코드 설명 & 느낀점
- 이중 반복문을 사용해 emergency를 반복하며, i < j 인 경우에 i의 순위(seq)를 1씩 더해준다.
  더해주는 이유는 숫자가 클수록 1순위어야 하기 때문이다. 2번째 for문이 종료된 후, answer에 seq(진료순서)를 append 해준다.
  seq는 1로 초기화해주어야 값이 중복되지 않기 때문에 첫번째 for문 바로 밑에 코드를 넣어 반복할 때 마다 seq를 1로 초기화해주었다.

  두번쨰 반복문 안에 seq 증감 연산이 있어 j 값에 대한 seq가 증가되는줄 알았는데,
  seq 값이 매번 i의 값을 기준으로 계산되고, i가 바뀔 때마다 seq가 다시 초기화되기 때문에 내가 생각한 것과 달리
  동작한다는 것을 알게되었다.  
