---
layout: single
title: "프로그래머스 - 문자열 묶기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120885)  

## 📌문자열 묶기
#### 📖문제 설명 :  
문자열 배열 strArr이 주어집니다. strArr의 원소들을 길이가 같은 문자열들끼리 그룹으로 묶었을 때 가장 개수가 많은 그룹의 크기를 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예  
|strArr|result|
|---|---|
|["a","bc","d","efg","hi"]|"101"|


<br>

#### ✏️정답 코드
```python
def solution(strArr):
    answer = 0
    str_len_dict = {}

    for i in strArr:
        length = len(i)
        if length not in str_len_dict: # length가 str_len_dic에 없다면
            str_len_dict[length] = 1 # 1로 초기화
        else: # length가 str_len_dic에 있다면
            str_len_dict[length] += 1 # 개수 1증가
    answer = max(str_len_dict.values())

    return answer
```

<br>

#### ✨코드 설명
- str_len_dict 딕셔너리 변수를 생성하고 반복문을 사용해 str_len_dict안에 key값(문자열 길이)이 있는지 유무를 판단했다.
  문자열 길이별로 분류했을 때, 개수가 많은 그룹의 크기를 반환해야하므로 key값을 문자열 길이로 주었고 value값은 str_len_dict에 없을경우 1로 초기화해주었다.
  str_len_dict에 key값(문자열길이)이 있다면 value값을 1증가시켜주었다. 반복한 후, max()함수를 사용해 value값이 가장 큰 것을 찾아 그 그룹의 크기를 answer에 넣어주었다. 
