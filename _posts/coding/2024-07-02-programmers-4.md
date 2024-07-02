---
layout: single
title: "프로그래머스 - 특정한 문자를 대문자로 바꾸기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181873)  

## 📌특정한 문자를 대문자로 바꾸기
#### 📖문제 설명 : 
영소문자로 이루어진 문자열 my_string과 영소문자 1글자로 이루어진 문자열 alp가   
매개변수로 주어질 때, my_string에서 alp에 해당하는 모든 글자를 대문자로 바꾼  
문자열을 반환하는 solution 함수를 작성해 주세요.


#### 입출력 예  

|my_string|alp|result|
|---|---|---|
|"programmers"|"p"|"Programmers"|
|"lowercase"|"x"|"lowercase"|  


#### ✏️코드
```python
def solution(my_string, alp):
    answer = ''

    for i in range(len(my_string)):
        if my_string[i] == alp:
            answer += my_string[i].upper() #대문자로 바꿔주기
        else:
            answer += my_string[i]
    return answer
```

<br>

#### ✨느낀점 
- upper() 함수를 사용해 해당 문자를 대문자로 쉽게 바꿀 수 있었습니다. 
