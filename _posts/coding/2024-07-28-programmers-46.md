---
layout: single
title: "프로그래머스 - 정수 제곱근 판별"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12934)  

## 📌정수 제곱근 판별

#### 📖문제 설명 :  
임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

#### 📖제한 사항 :  
- n은 1이상, 50000000000000 이하인 양의 정수입니다.
  
#### 📖입출력 예 : 

|n|result|
|---|---|
|121|144|
|3|-1|

#### 📖입출력 예 설명 : 

입출력 예#1
- 121은 양의 정수 11의 제곱이므로, (11+1)를 제곱한 144를 리턴합니다.

입출력 예#2
- 3은 양의 정수의 제곱이 아니므로, -1을 리턴합니다.

#### ✏️오류 코드
```python
from math import sqrt
def solution(n):
    answer = 0
    sqrt_n = sqrt(n)
    
    if n == sqrt_n * sqrt_n: # 오류발생 
        answer = (sqrt_n + 1) * (sqrt_n + 1)
    else:
        answer = -1

    return int(answer)
```

- 문제점 : sqrt(n)은 부동 소수점 값을 반환한다. 여기서 sqrt_n이 정수가 아니더라도 (sqrt_n * sqrt_n)와 n이 같지 않을 수 있기 때문에
  부동 소수점 비교에서 정확도가 떨어질 수 있기 때문에 오류가 발생한다. 

#### ✏️정답 코드
```python
from math import sqrt
def solution(n):
    answer = 0
    sqrt_n = sqrt(n)
    
    if sqrt_n == int(sqrt_n): # 부동 소수점 값이 정수인지 확인
        answer = (sqrt_n + 1) * (sqrt_n + 1)
    else:
        answer = -1

    return int(answer)
```

<br>

#### ✨코드설명
- 제곱근인지 판별하기 위해 sqrt()함수를 사용해 부동 소수점 값을 찾아주었다.
  sqrt(n)을 해서 sqrt_n 변수에 값을 넣어주고, 이 값이 정수인 경우에만 sqrt_n에 1을 더해준 값의 제곱수를 반환해준다.
  sqrt_n이 정수인지 확인하는 이유는 양의 정수의 제곱으로 표현될 수 있는 수가 제곱수이기 때문에 정수인지 확인해주는 코드가 필요하다.  

  위 코드의 반례로 101이 매개변수값으로 들어온다면, sqrt(101) = 10.049로 정수인지 확인하지 않고 처음 작성했던 코드를 따라가게되면
  10.049 * 10.049 = 100.9로 반올림되어 101과 같아지므로 11 * 11 인 122의 값이 answer에 들어가게된다.
  이러한 오류를 막기위해 정수인지 확인하는 과정을 거쳐야한다. 
  
