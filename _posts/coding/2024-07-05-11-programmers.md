---
layout: single
title: "프로그래머스 - 접미사인지 확인하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181908)  

## 📌접미사인지 확인하기
#### 📖문제 설명 :  
어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다. 예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.
문자열 my_string과 is_suffix가 주어질 때, is_suffix가 my_string의 접미사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예  

|my_string|is_suffix|result|
|---|---|---|
|"banana"|"ana"|1|
|"banana"|"nan"|0|
|"banana"|"wxyz"|0|
|"banana"|"abanana"|0|


<br>

#### ✏️코드
```python
def solution(my_string, is_suffix):
    answer = 0

     # is_suffix 문자열이 my_string 문자열 오른쪽에서 몇번째 위치에 있는지 계산
    pos = len(my_string) - my_string.rfind(is_suffix)
    if pos == len(is_suffix):
        answer = 1  # 접미사 맞으면 1 리턴
    else:
        answer = 0  # 접미사가 아니면 0 리턴

    return answer
```

<br>

#### ✨느낀점 
- '접두사인지 확인하기' 문제는 비교해주면 쉽게 풀 수 있었는데, 이번 문제는 어렵게 다가왔다. 우선 이 문제를 풀기위해서는 rfind()함수를 알아야했다.
  rfind()를 사용해 is_suffix 문자열의 마지막 위치를 찾아주어 my_string문자열 길이에서 빼주면 is_suffix문자열이 몇번째에 위치하는지 구할 수 있었는데,
  이러한 생각을 해내는 것이 이번 문제에서 좀 어려웠다. 파이썬 함수를 많이 공부해야함을 느꼈다.  
  
  
