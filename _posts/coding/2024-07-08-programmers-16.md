---
layout: single
title: "프로그래머스 - 배열의 길이를 2의 거듭제곱으로 만들기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181857)  

## 📌배열의 길이를 2의 거듭제곱으로 만들기
#### 📖문제 설명 :  
정수 배열 arr이 매개변수로 주어집니다. arr의 길이가 2의 정수 거듭제곱이 되도록 arr 뒤에 정수 0을 추가하려고 합니다. arr에 최소한의 개수로 0을 추가한 배열을 return 하는 solution 함수를 작성해 주세요.

#### 입출력 예 

|arr|result|
|---|---|
|[1, 2, 3, 4, 5, 6]|[1, 2, 3, 4, 5, 6, 0, 0]|
|[58, 172, 746, 89]|[58, 172, 746, 89]|

<br>

#### ✏️내 코드
```python
def solution(arr):
    while(True) :
        if len(arr) & len(arr)-1 == 0 : #2의 거듭제곱수인지 확인
            return arr
        else : #2의 거듭제곱이 아니라면
            arr.append(0)
            
    return answer
```

<br>

#### ✨느낀점
- 2의 거듭제곱을 구하는 방법을 알면 쉽게 풀 수 있는 문제인 거 같다.
  수학도 열심히 공부해야겠다는 생각이 들었다.
  너무 어렵게 생각하고 문제를 풀려고 하지말아야겠다는 생각이 들었다. 
  
  
