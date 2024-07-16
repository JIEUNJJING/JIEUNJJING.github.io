---
layout: single
title: "프로그래머스 - 외계어 사전"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120869)  

## 📌외계어 사전
#### 📖문제 설명 :  
PROGRAMMERS-962 행성에 불시착한 우주비행사 머쓱이는 외계행성의 언어를 공부하려고 합니다. 알파벳이 담긴 배열 spell과 외계어 사전 dic이 매개변수로 주어집니다. spell에 담긴 알파벳을 한번씩만 모두 사용한 단어가 dic에 존재한다면 1, 존재하지 않는다면 2를 return하도록 solution 함수를 완성해주세요.

#### 입출력 예 

|arr|k|result|
|---|---|---|
|["p", "o", "s"]|["sod", "eocd", "qixm", "adio", "soo"]|2|
|["z", "d", "x"]|["def", "dww", "dzx", "loveaw"]|1|
|["s", "o", "m", "d"]|["moos", "dzx", "smm", "sunmmo", "som"]|2|

<br>

#### ✏️정답 코드
```python
def solution(spell, dic):

    for i in dic:
        if sorted(i) == sorted(spell):
            return 1
    return 2
```

<br>

#### ✨코드설명
- spell에 담긴 알파벳을 한번씩만 모두 사용한 단어가 dic에 존재하면 1을 반환하고 아니면 2를 반환해준다.
  다 있는지 확인하기 위해 spell과 dic을 다 정렬해준 후 비교했을 때, 다 같으면 1을 반환하도록 코드를 작성하였다.
  없다면 for문 반복을 다 하고난 후 반복문을 빠져나와 2를 반환해준다. 
