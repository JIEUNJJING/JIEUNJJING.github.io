---
layout: single
title: "프로그래머스 - 서울에서 김서방 찾기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12919)  

## 📌서울에서 김서방 찾기

#### 📖문제 설명 :  
String형 배열 seoul의 element중 "Kim"의 위치 x를 찾아, "김서방은 x에 있다"는 String을 반환하는 함수, solution을 완성하세요. seoul에 "Kim"은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

#### 📖제한 사항 :  
- seoul은 길이 1 이상, 1000 이하인 배열입니다.
- seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.
- "Kim"은 반드시 seoul 안에 포함되어 있습니다.
  
#### 📖입출력 예 : 

|seoul|return|
|---|---|
|["Jane", "Kim"]|"김서방은 1에 있다"|

#### ✏️나의 코드
```python
def solution(seoul):
    answer = ''

    for i in seoul:
        if i == 'Kim':
            answer = '김서방은 ' + str(seoul.index(i)) + '에 있다'
    return answer
```

#### ✏️다른 사람 코드
```python
def findKim(seoul):
    # 함수를 완성하세요

    return "김서방은 {}에 있다".format(seoul.index('Kim'))
```

<br>

#### ✨코드설명
- 나는 seoul 리스트를 반복하며 Kim이 있을 경우, 그 인덱스를 찾아 문자열을 '+'로 연결하여 문장을 출력해주는 방식을 사용했다.
  다른 사람들의 코드를 보니 다양한 방법으로 많이 풀었지만, 위의 예시와 같이 '.format()' 을 사용해 한줄로도 코드를 작성할 수 있었다.
  다른 사람들의 코드도 보며 어떤 방법으로 풀면 더 쉽고 간단하게 풀 수 있는지 공부해야겠다. 
