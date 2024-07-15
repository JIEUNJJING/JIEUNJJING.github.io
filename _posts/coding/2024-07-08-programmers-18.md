---
layout: single
title: "프로그래머스 - 숨어있는 숫자의 덧셈 (2)"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120864)  

## 📌숨어있는 숫자의 덧셈 (2)
#### 📖문제 설명 :  
문자열 my_string이 매개변수로 주어집니다. my_string은 소문자, 대문자, 자연수로만 구성되어있습니다. my_string안의 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예  

|arr|result|
|---|---|
|"aAb1B2cC34oOp"|37|
|"1a2b3c4d123Z"|133|

<br>

#### ✏️내 코드
```python
def solution(my_string):
    answer = 0

    for i in my_string:
        if i.isalpha(): # 문자라면
            my_string = my_string.replace(i, ' ') # 공백으로 대체하기
    my_string = my_string.split() # 공백 기준으로 분할
    
    # my_string요소를 int로 변환해 숫자들을 모두 더해줌
    answer = sum(map(int, my_string))

    return answer

```

<br>

#### ✨느낀점
- 숫자만 더해주기위해 replace함수를 사용해 문자를 모두 공백으로 바꿔주었다.
  그러고 공백을 기준으로 분할해주고 map함수를 사용해 각 요소를 int형으로 변환해주어 모두 더해준 값을 반환해준다.

   map함수에 대해 알게되었고, 아직 map함수 사용법과 기본 형태 등 잘 모르기 때문에 좀 더 공부를 해야할 거 같다. 
  
  
