---
layout: single
title: "프로그래머스 - 문자열 잘라서 정렬하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181866)  

## 📌문자열 잘라서 정렬하기
#### 📖문제 설명 :  
문자열 myString이 주어집니다. "x"를 기준으로 해당 문자열을 잘라내 배열을 만든 후 사전순으로 정렬한 배열을 return 하는 solution 함수를 완성해 주세요.

단, 빈 문자열은 반환할 배열에 넣지 않습니다.
#### 입출력 예 

|myString|result|
|---|---|
|"axbxcxdx"|["a","b","c","d"]|
|"dxccxbbbxaaaa"|["aaaa","bbb","cc","d"]|

<br>

#### ✏️정답 코드
```python
def solution(myString):
    answer = []

    myString = myString.split('x')
    for i in myString:
        if i != '':
            answer.append(i)

    answer.sort()
    return answer
```

<br>

#### ✨코드설명
- 처음에 코드를 작성할 때, replace()함수를 사용했는데 split()함수를 사용하는것이 더 간단할 거 같아서 이렇게 코드를 작성했다.
  ''이거를 삭제하는것보다 ''아닌 것을 answer에 추가해주는 것이 코드에도 좋고 더 수월하다고 생각해 더해주는 방식으로 코드를 작성했다.
  다 추가해준 후 마지막에 정렬을하여 값을 반환해주면 된다. 
