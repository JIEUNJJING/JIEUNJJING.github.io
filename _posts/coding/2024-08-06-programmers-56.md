---
layout: single
title: "프로그래머스 - 문자열 밀기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120921)  

## 📌문자열 밀기

#### 📖문제 설명 :  
문자열 "hello"에서 각 문자를 오른쪽으로 한 칸씩 밀고 마지막 문자는 맨 앞으로 이동시키면 "ohell"이 됩니다. 이것을 문자열을 민다고 정의한다면 문자열 A와 B가 매개변수로 주어질 때, A를 밀어서 B가 될 수 있다면 밀어야 하는 최소 횟수를 return하고 밀어서 B가 될 수 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

#### 📖제한 사항 :  
- 0 < A의 길이 = B의 길이 < 100
- A, B는 알파벳 소문자로 이루어져 있습니다.
  
#### 📖입출력 예 : 

|A|B|result|
|---|---|---|
|"hello"|"ohell"|1|
|"apple"|"elppa"|-1|
|"atat"|"tata"|1|
|"abc"|"abc"|0|

#### 😅 오류 코드  
```python
def solution(A, B):
    answer = -1

    for i in range(len(A)): # A길이만큼 반복 
        if A == B:# A와 B가 같다면
            answer = 1 # 1 반환
            break
        A = A[-1] + A[0:len(A) - 1] # A와 B가 다르면, 맨 뒤 문자를 제일 앞으로 옮겨 다시 비교
    return answer
```
이렇게 코드를 작성했을 때, 0이 반환되지 않는 문제점이 있어서 answer초기 값을 0으로 주었더니 -1이 반환되지 않는 문제가 발생했다,
생각해보니 0, 최소 반환 횟수, -1 을 반환해주는 코드가 다 없어서 그랬던 것이다. 심지어 최소 반환횟수를 반환해주는 문제인데 문제를 잘못읽고 1을 반환해줘야하는줄알고 있었다..

#### ✏️ 정답 코드  
```python
def solution(A, B):
    answer = 0

    if A == B: # A와 B가 같은 경우 
        return 0
    for i in range(len(A)): # A길이만큼 반복 
        if A == B:# A와 B가 같은지 확인
            answer = i 
            break
        A = A[-1] + A[0:len(A) - 1] # A와 B가 다르면, 맨 뒤 문자를 제일 앞으로 옮겨 다시 비교
    if A != B:
        answer = -1
    return answer
```
제일 위에 A와 B가 같으면 0을 반환해주는 코드와, answer = 1에서 answer = i로 바꿔 최소 횟수 반환 코드를 주고, 반복문을 다 돌았을 때도 같은 문자가 없었다면 
-1을 반환해주는 코드를 추가해주었더니 성공했다. 

#### ✏️ 다른사람 코드  
```python
def solution(A, B):
    answer = -1
    a_len = len(A)

    for i in range(a_len): # A길이만큼 반복 
        if(A == B): # A와 B가 같다면
            answer = i # 첫번째 비교라 i에 0이 들어가 있음(0 반환)
            break
        A = A[-1] + A[0:a_len-1] # 젤 뒤에 문자를 젤 앞으로 보내줌

    return answer
```
코드 분석 : A길이만큼 반복문을 반복하는데 처음에는 i에 0이 들어가있고, A와 B가 같다면 answer에 바로 i(=0)를 넣어주어
            break를 사용해 반복문을 종료하게된다. 그럼 0이 반환된다. 만약 A와 B가 같지 않다면, 맨 마지막 문자를 제일 앞에 붙여주어 다시 비교하는 과정을 반복한다.
            answer의 초기 값을 -1로 주었기 때문에 반복문이 끝나고도 A와 B가 같지 않다면 -1이 반환되게 된다.

#### ✨코드 분석 & 느낀점 
- 문제를 꼼꼼히 잘 읽었다고 생각했는데.. 이런 실수를 하다니.. 문제를 읽었어도 또 읽고 또 읽어봐야겠다🥲
  이런 사소한 실수부터 줄이도록 노력해야겠다. 그래도 실패는 성공의 어머니라고..^^! 앞으로도 더 파이팅하자~!


  
