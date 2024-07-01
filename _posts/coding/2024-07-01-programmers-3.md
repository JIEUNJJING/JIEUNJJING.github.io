---
layout: single
title: "프로그래머스 - 소문자로 바꾸기"
categories: 
  - coding
tag:
  - python, coding, grammar
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181876)  

## 📌소문자로 바꾸기
#### 📖문제 설명 :  
![image](./image/programmers.png)


#### 입출력 예  

|n_str|result|
|---|---|
|"aBcDeFg"|"abcdefg"|
|"aaa"|"aaa"|  


<br>

#### ✏️코드
```python
def solution(myString):
    answer = ''

    for i in myString:
        if (97 <= ord(i) <= 122):
            answer += (i)
        else:
            answer += chr(ord(i) + 32)
    return answer
```

<br>

#### ✨느낀점 
- ord() 함수를 사용해 쉽게 아스키 코드 값을 찾을 수 있었고, 구한 아스키코드 값에 32를 더해주어
  소문자가 되도록 하였습니다. 
  
