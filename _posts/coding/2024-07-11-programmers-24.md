---
layout: single
title: "프로그래머스 - 한 번만 등장한 문자"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120896)  

## 📌한 번만 등장한 문자
#### 📖문제 설명 :  
문자열 s가 매개변수로 주어집니다. s에서 한 번만 등장하는 문자를 사전 순으로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요. 한 번만 등장하는 문자가 없을 경우 빈 문자열을 return 합니다.

#### 입출력 예  
|s|result|
|---|---|
|"abcabcadc"|"d"|
|"abdc"|"abcd"|
|"hello"|"eho"|

<br>

#### ✏️정답 코드
```python
def solution(s):
    answer = ''
    a = []

    for i in s:
        if s.count(i) == 1:
            a.append(i) 
    a.sort()
    a = "".join(a)
    answer = a
    return answer
```

<br>

#### ✨코드 설명
- 문자열 안에서 한 번만 등장문자를 찾기위해 count 함수를 사용해 조건문을 작성하였고, 조건이 맞을 경우 a라는 배열에 넣어주었다.
  그리고 sort함수를 사용해 정렬해준 뒤 출력하게되면 리스트 형태로 나오기 때문에, join함수를 사용해 문자열 형태로 나오게 바꿔주어 출력했다. 
  
#### ✨느낀점
- count 함수를 몰라서 문제를 풀기 어려웠는데, count함수를 사용하니 쉽게 문제를 풀 수 있었다. 나는 a라는 배열을 만들어주어 풀었는데,
  다른 사람들의 풀이를 보니 배열을 사용하지 않고 더 쉽고 간단하게 코드를 짠 사람들이 많아서 새로운 방법으로 풀 수 있는 방법을 공부할 수 있었다.
   
