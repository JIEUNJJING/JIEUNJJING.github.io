---
layout: single
title: "프로그래머스 - 세 개의 구분자"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120835)  

## 📌세 개의 구분자
#### 📖문제 설명 :  
임의의 문자열이 주어졌을 때 문자 "a", "b", "c"를 구분자로 사용해 문자열을 나누고자 합니다.
예를 들어 주어진 문자열이 "baconlettucetomato"라면 나눠진 문자열 목록은 ["onlettu", "etom", "to"] 가 됩니다.
문자열 myStr이 주어졌을 때 위 예시와 같이 "a", "b", "c"를 사용해 나눠진 문자열을 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.
단, 두 구분자 사이에 다른 문자가 없을 경우에는 아무것도 저장하지 않으며, return할 배열이 빈 배열이라면 ["EMPTY"]를 return 합니다.
#### 입출력 예  
|myStr|result|
|---|---|
|"baconlettucetomato"|["onlettu", "etom", "to"]|
|"abcd"|["d"]|
|"cabab"|["EMPTY"]|

<br>

#### ✏️내 코드
```python
def solution(myStr):
    answer = []

    for i in myStr:
        if i == "a" or i == "b" or i == "c":
            myStr = myStr.replace(i, " ")
    answer = myStr.split()
    
    return answer

```

<br>

#### ✨코드 설명 & 느낀점
- 반복문을 돌며 a, b, c 문자가 있으면 replace함수를 사용해 문자를 공백으로 바꾸어 주었다. split()을 사용해 공백을 기준으로 구분해주면
  쉽게 문제를 풀 수 있다.

  사용했던 함수들을 계속 사용하니 이젠 조금 익숙해지기도 했고, 문제를 봤을 때 어떤 함수를 써야할지 조금씩 보이는 거 같다. 
