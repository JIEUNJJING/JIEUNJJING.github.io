---
layout: single
title: "프로그래머스 - x 사이의 개수"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[프로그래머스 0 떼기](https://school.programmers.co.kr/learn/courses/30/lessons/181867)  

## 📌x 사이의 개수
#### 📖문제 설명 :  
문자열 myString이 주어집니다. myString을 문자 "x"를 기준으로 나눴을 때 나눠진 문자열 각각의 길이를 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예  

|n_str|result|
|---|---|
|"oxooxoxxox"|[1, 2, 1, 0, 1, 0]|
|"xabcxdefxghi"|[0, 3, 3, 3]|  


<br>

#### ✏️첫 번째 코드 (예시 1번 사용)
```python
def solution(myString):
    answer = []
    a = myString.split("x") # ['o', 'oo', 'o', '', 'o', ''] 이렇게 a에 들어감

    for i in a:
        answer.append(len(i))
    
    return answer
```

<br>

#### ✨느낀점 
- 이 문제를 어떻게 해결하면 좋을지 고민을 하며 문제를 풀다가 힌트를 얻었는데, split()함수를 사용하면 간단히 해결할 수 있었다.
  spilt()함수를 사용해 우선 myString 문자열을 분리해준 후, 각각 길이를 구해 answer에 값을 넣어주면 된다.   
  
