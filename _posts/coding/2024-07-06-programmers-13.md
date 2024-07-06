---
layout: single
title: "프로그래머스 - 접미사 배열"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181909)  

## 📌접미사 배열
#### 📖문제 설명 :  
어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다. 예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.
문자열 my_string이 매개변수로 주어질 때, my_string의 모든 접미사를 사전순으로 정렬한 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예  

|binomial|result|
|---|---|
|"banana"|["a", "ana", "anana", "banana", "na", "nana"]|
|"programmers"|["ammers", "ers", "grammers", "mers", "mmers", "ogrammers", "programmers", "rammers", "rogrammers", "rs", "s"]|

<br>

#### ✏️내 코드
```python
def solution(my_string):
    answer = []
    
    for i in range(len(list(my_string))):
        answer.append(my_string[i:])

    answer.sort()
    return answer
```

#### ✏️다른사람 코드
```python
def solution(my_string):
    answer = []
    for i in range(len(my_string)):
        answer.append(my_string[-i:])
    answer.sort()
    return answer
```

<br>

#### ✨구현 방법 
- 어떻게 구현하면 좋을지 생각하다 낸 아이디어는 my_string문자열을 리스트로 바꿔주어 answer에 넣어준다.
  여기서 **answer.append(my_string[i:])** 여기를 보면 i번째부터 끝까지 넣어주기 때문에 처음에는 "banana", 두번째 반복문이 돌 때는, i가 1이 되어 1부터 끝까지인 "anana" 이런식으로
  answer에 들어가게된다. 그러고나서 sort를 사용해 정렬해주었다.

#### ✨느낀점
- 다른 사람들의 풀이를 보니 다들 my_string을 list로 바꾸지않고 바로 사용했는데, 생각해보니 문자열도 슬라이싱이 가능하기 떄문에
  굳이 list로 바꾸어주지 않아도 되겠다는 것을 깨달았다. 다음번엔 좀 더 간결하고 가독성이 좋은 코드를 쓰기위해 열심히 공부를 해야겠다. 
  
  
