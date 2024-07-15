---
layout: single
title: "프로그래머스 - 소인수분해"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120852)  

## 📌소인수분해
#### 📖문제 설명 :  
소인수분해란 어떤 수를 소수들의 곱으로 표현하는 것입니다. 예를 들어 12를 소인수 분해하면 2 * 2 * 3 으로 나타낼 수 있습니다. 따라서 12의 소인수는 2와 3입니다. 자연수 n이 매개변수로 주어질 때 n의 소인수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예  

|n|result|
|---|---|
|12|[2, 3]|
|17|[17]|
|420|[2, 3, 5, 7]|


<br>

#### ✏️정답 코드
```python
def solution(n):
    answer = []
    i = 2
    while (i <= n): # 소인수라 n보다 작거나 같음
        if n % i == 0: # 나머지가 0이라면 
            answer.append(i) # i값 추가
            n = n // i # n // i해서 나온 값으로 n을 바꿔줌
        else: # 나머지가 0이 아니라면 
            i += 1 # 소인수를 찾기위해 2부터 시작해 1씩 증가하며 찾아주기위해
    answer = list(sorted(set(answer))) # 중복된값 삭제 : set()
    return answer 
```

<br>

#### ✨코드 설명
- 소인수는 n값보다 작거나 같기때문에, i를 2로 초기화해주고 while문 조건을 i <= n 이렇게 주었다.
  n을 i로 나누었을 때 나머지가 0이라면, answer에 i값을 추가해준다. 만약 나머지가 0이 아니라면 소인수를 찾아야하기 때문에 i값을 1증가시켜준 후,
  다시 반복한다. 그리고 중복된 값을 없애주기위해 set()함수를 사용하였고, set()함수는 순서가 없기 때문에 sorted()함수로 정렬해준 후 리스트로 변경하여 값을 반환해주었다. 
