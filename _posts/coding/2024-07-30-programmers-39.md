---
layout: single
title: "프로그래머스 - 같은 숫자는 싫어"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12906)  

## 📌같은 숫자는 싫어

#### 📖문제 설명 :  
배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다. 이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. 예를 들면,

- arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
- arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.
  
배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

#### 📖제한 사항 :  
- 배열 arr의 크기 : 1,000,000 이하의 자연수
- 배열 arr의 원소의 크기 : 0보다 크거나 같고 9보다 작거나 같은 정수
  
#### 📖입출력 예 : 

|arr|return|
|---|---|
|[1,1,3,3,0,1,1]|[1,3,0,1]|
|[4,4,4,3,3]|[4,3]|

#### ✏️오류 코드
```python
def solution(arr):
    answer = []
    a = []

    for i in range(1, len(arr)):
        if arr[i] != arr[i + 1]:
            a.append(arr[i])

    answer = a
    return answer
```

#### ✏️정답 코드
```python
def solution(arr):
    answer = []
    a = [arr[0]]
    
    for i in range(1, len(arr)):
        if arr[i] != a[-1]:
            a.append(arr[i])
    answer = a

    return answer
```


<br>

#### ✨코드설명
- 처음에 문제를 봤을 때, for문을 사용해 현재 값과 다음에있는 값이 다른경우 a라는 새로운 배열에 넣어주는 코드를 작성하려고 했었다.
  하지만 자꾸 **IndexError: list index out of range** 이 오류가 발생했고, if문 부분을 if arr[i] != arr[i - 1] 이렇게 바꾸었을 때,
  인덱스 오류는 없어졌지만, 값이 제대로 나오지 않았다. 그래서 새로운 방법으로 새로운 배열 a에 arr[0]을 넣어 초기화하고,
  반복문을 돌며 현재 arr값과 a배열 마지막에 들어있는 원소 값이 다를경우에 a에 값을 넣어주는 코드로 바꿨다.
  이렇게 코드를 작성했더니 정상적으로 동작되었다. 
