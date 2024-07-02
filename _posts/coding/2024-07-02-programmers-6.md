---
layout: single
title: "프로그래머스 - l로 만들기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181834)  

## 📌l로 만들기
#### 📖문제 설명 : 
알파벳 소문자로 이루어진 문자열 myString이 주어집니다. 알파벳 순서에서 "l"보다 앞서는 모든 문자를 "l"로 바꾼 문자열을 return 하는 solution 함수를 완성해 주세요.

#### 입출력 예  

|myString|result|
|---|---|
|"abcdevwxyz"|"lllllvwxyz"|
|"jjnnllkkmm"|"llnnllllmm"|

#### ✏️내가 쓴 코드(틀림)
```python
def solution(myString):
    answer = ''

    for i in range(len(myString)):
        if myString[i] < "l":
            myString[i] = "l"
    answer= myString
    return answer
```

#### ✏️정답 코드
```python
def solution(myString):
    answer = ''
    myString = list(myString) # 리스트로 변환

    for i in range(len(myString)):
        if myString[i] < "l":
            myString[i] = "l"
    answer= ''.join(myString) #리스트를 다시 문자열로 변환
    return answer
```

<br>

#### ✨틀린 이유
- 문자열(string)은 인덱스로 접근 가능하고, 리스트와 같이 슬라이싱도 가능합니다.
  하지만, 요소를 바꾸는 것은 불가능합니다. (= 아이템 배치를 지원하지 않는다.)
  replace를 사용해 바꾸거나, 리스트로 변환 후 바꾸는 방법이 있습니다. 

#### ✨고친점
- 문자열을 리스트로 변환해주어 l보다 작은 값들을 바꿔준 후, 다시 join함수를 사용해 문자열로 변환해주었습니다. 
