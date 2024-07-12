---
layout: single
title: "프로그래머스 - 이진수 더하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120885)  

## 📌이진수 더하기
#### 📖문제 설명 :  
이진수를 의미하는 두 개의 문자열 bin1과 bin2가 매개변수로 주어질 때, 두 이진수의 합을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예  
|bin1|bin2|result|
|---|---|---|
|"10"|"11"|"101"|
|"1001"|"1111"|"11000"|

<br>

#### ✏️정답 코드
```python
def solution(bin1, bin2):
    answer = ''
    num1 = int(bin1, 2) # 2진수 문자열을 10진수 정수로 변환
    num2 = int(bin2, 2)
    sum = num1 + num2 

    answer = bin(sum).replace("0b", "") # 10진수를 이진수로 변환 후, 0b 제거
    
    return answer
```

<br>

#### ✨코드 설명
- int() 함수와 bin()함수를 사용하면 쉽게 구현이 가능하다. int()함수를 사용해 2진수 문자열을 10진수 정수로 바꿔주었고,
  바꿔준 두 정수를 더하여 sum변수에 넣어준 후 다시 이진수로 바꾸기위해 bin()함수를 사용했다. 이진수를 출력하면 앞에 2진수를 뜻하는 "0b"가 붙어서 나오는데
  이것을 없애주기위해 replace()함수를 사용했다. 
  
#### ✨느낀점
- 반복문을 사용해 코드를 짜야할지 고민하고 있었는데 다른 사람들의 풀이를 보니 함수를 사용해 간단히 구현한 코드를 보고 새로운 함수들을 공부할 수 있었다.
  나는 replace함수를 사용해 "0b"를 없애주었지만 다른 사람들은 문자열 슬라이싱을 사용해 없애주는 코드를 짠 사람들도 많이 있었다. 
   
