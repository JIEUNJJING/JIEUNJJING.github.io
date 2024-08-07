---
layout: single
title: "프로그래머스 - 저주의 숫자 3"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120871)  

## 📌저주의 숫자 3
#### 📖문제 설명 :  
3x 마을 사람들은 3을 저주의 숫자라고 생각하기 때문에 3의 배수와 숫자 3을 사용하지 않습니다. 3x 마을 사람들의 숫자는 다음과 같습니다.

|10진법|3x 마을에서 쓰는 숫자|10진법|3x 마을에서 쓰는 숫자|
|---|---|---|---|
|1|1|6|8|
|2|2|7|10|
|3|4|8|11|
|4|5|9|14|
|5|7|10|16|  

정수 n이 매개변수로 주어질 때, n을 3x 마을에서 사용하는 숫자로 바꿔 return하도록 solution 함수를 완성해주세요.

#### 📖제한 사항 :  
- 1 ≤ n ≤ 100
#### 📖입출력 예 : 

|n|result|
|---|---|
|15|25|
|40|76|

#### 📖입출력 예 설명 : 
입출력 예 #1  
- 15를 3x 마을의 숫자로 변환하면 25입니다.
   
입출력 예 #2  
- 40을 3x 마을의 숫자로 변환하면 76입니다.

#### ✏️정답 코드
```python
def solution(n):
    answer = 0
    i = 1

    while (n):
        if i % 3 != 0 and '3' not in str(i):
            n -= 1
        i += 1
        answer = i - 1
    return answer
```

<br>

#### ✨코드설명
- 매개변수로 받은 숫자인 n이 될때까지 반복하는 while문을 작성하고, 숫자에 3이 포함되지 않거나 3의 배수가 아닌 경우에는
  n -=1 을 주어 n을 감소시켜준다. 만약 조건을 만족하지 않는다면, i += 1을 주어 1을 더해준다.
  이렇게 코드를 작성하면 3의 배수 또는 3이 포함된 숫자를 사용하지않을 수 있다. answer = i - 1을 해준 이유는 현재 i는 바로 위의 코드인 i += 1
  때문에 1이 더해진 다음 숫자를 가리키고 있어 1을 빼주어야 한다.  
  
