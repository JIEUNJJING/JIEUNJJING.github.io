---
layout: single
title: "프로그래머스 - 0 떼기"
categories: 
  - coding
tag:
  - python, coding, grammar
--- 
[프로그래머스 0 떼](https://school.programmers.co.kr/learn/courses/30/lessons/181847)  

## 📌꼬리 문자열
#### 📖문제 설명 :  
정수로 이루어진 문자열 n_str이 주어질 때, n_str의 가장 왼쪽에 처음으로 등장하는  
0들을 뗀 문자열을 return하도록 solution 함수를 완성해주세요.  

#### 입출력 예  

|n_str|result|
|---|---|
|"0010"|"10"|
|"854020"|"854020"|  


<br>

#### ✏️첫 번째 코드
```python

def solution(n_str):
    answer = ''

    answer = n_str.lstrip("0")
    
    return answer
```

<br>

#### ✨느낀점 
- 이 문제를 어떻게 해결하면 좋을지 고민을 하다가 strip() 함수를 알게되어
  쉽게 문제를 해결할 수 있었습니다.  
  
