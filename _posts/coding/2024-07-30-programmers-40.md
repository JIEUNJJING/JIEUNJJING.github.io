---
layout: single
title: "프로그래머스 - 이상한 문자 만들기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12930)  

## 📌이상한 문자 만들기

#### 📖문제 설명 :  
문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

#### 📖제한 사항 :  
- 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
- 첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.
  
#### 📖입출력 예 : 

|s|return|
|---|---|
|"try hello world"|"TrY HeLlO WoRlD"|

#### ✏️정답 코드
```python
def solution(s):
    answer = []
    s = list(s.split(' '))

    for i in s: #i에 try, hello, world 이렇게 들어옴
        new_word = ''
        for index, char in enumerate(i): # i의 인덱스값과 문자를 각각 index와 char에 넣음
            if index % 2 == 0: # 인덱스가 짝수일 경우
                new_word += char.upper() # 대문자로 변환해 new_word에 넣어줌
            else: # 홀수일 경우
                new_word += char.lower() # 소문자로 변환해 new_word에 넣어줌
        answer.append(new_word) # TrY, HeLlo, WoRlD이렇게 각각 answer에 추가함
    
    return ' '.join(answer) # 리스트를 문자열로 변환
```


<br>

#### ✨코드설명
- 짝수번째일 때, 대문자로 바꾸고 홀수번째일 때 소문자로 바꾸는 과정에서 좀 막혔었다.
  어떻게 해결해야할지 생각이 안나서 다른 사람들의 코드를 조금 참고하였다. 이 문제를 통해 enumerate 함수를 알게되었다.
  이 함수를 통해 인덱스 값과 문자를 각각 받아와 짝수번째일 경우 문자를 쉽게 바꿔줄 수 있었다.
  코드를 읽으면 어떻게 돌아가고 어떤 결과가 나오는지 알 수 있는데, 내가 코드를 짜려고 하니 막히는 부분이 좀 생기는 거 같다.
  이러한 문제를 해결하려면 코드 문제를 더 많이 풀어보는 연습을 해야할 거 같다.
