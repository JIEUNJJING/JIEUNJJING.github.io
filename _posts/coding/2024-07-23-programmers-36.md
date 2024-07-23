---
layout: single
title: "프로그래머스 - 왼쪽 오른쪽"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181890)  

## 📌왼쪽 오른쪽
#### 📖문제 설명 :  
문자열 리스트 str_list에는 "u", "d", "l", "r" 네 개의 문자열이 여러 개 저장되어 있습니다. str_list에서 "l"과 "r" 중 먼저 나오는 문자열이 "l"이라면 해당 문자열을 기준으로 왼쪽에 있는 문자열들을 순서대로 담은 리스트를, 먼저 나오는 문자열이 "r"이라면 해당 문자열을 기준으로 오른쪽에 있는 문자열들을 순서대로 담은 리스트를 return하도록 solution 함수를 완성해주세요. "l"이나 "r"이 없다면 빈 리스트를 return합니다.

#### 입출력 예 

|str_list|result|
|---|---|
|["u", "u", "l", "r"]|["u", "u"]|
|["l"]|[]|

<br>

#### ✏️정답 코드
```python
def solution(str_list):
    answer = []

    for i in str_list:
        if i == 'l':
            answer = str_list[0:str_list.index(i)]
            break
        elif i == 'r':
            answer = str_list[str_list.index(i) + 1:]
            break
        else:
            answer = []

    return answer
```

<br>

#### ✨코드설명
- 앞에서 푼 문제를 활용해 index()함수를 사용하였다. 처음 코드에서 else문을 빼고 실행하니 자꾸 테스트 케이스를 통과하지 못했는데,
  else문을 추가하고나서 성공할 수 있었다. 슬라이싱을 사용해 문제를 푸니 훨씬 코드도 짧고 쉽게 풀 수 있었다. 
  
