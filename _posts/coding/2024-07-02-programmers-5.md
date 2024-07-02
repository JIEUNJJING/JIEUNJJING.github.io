---
layout: single
title: "프로그래머스 - 배열의 원소 삭제하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181844)  

## 📌배열의 원소 삭제하기
#### 📖문제 설명 : 
정수 배열 arr과 delete_list가 있습니다. arr의 원소 중 delete_list의 원소를  
모두 삭제하고 남은 원소들은 기존의 arr에 있던 순서를 유지한 배열을 return 하는 solution 함수를 작성해 주세요.


#### 입출력 예  

|arr|delete_list|result|
|---|---|---|
|[293, 1000, 395, 678, 94]|[94, 777, 104, 1000, 1, 12]|[293, 395, 678]|
|[110, 66, 439, 785, 1]|[377, 823, 119, 43]|[110, 66, 439, 785, 1]|  

#### ✏️내가 쓴 코드(틀림)
```python
def solution(arr, delete_list):
    answer = []
    
    for i in range(len(arr)):
        if arr[i] in delete_list:
            del arr[i]
        else:
            answer.append(arr[i])
    
    return answer
```

#### ✏️정답 코드
```python
def solution(arr, delete_list):
    answer = []
    
    for i in arr:
        if i not in delete_list:
            answer.append(i)
    
    return answer
```

<br>

#### ✨틀린 이유
- del arr[i] 이 코드를 사용하게되면, 반복문이 진행되는 동안 리스트의 요소를 삭제하게되어 리스트의 길이가 변경됩니다.
  이러한 상황으로 인해 인덱스가 맞지 않게 되어 'IndexError'가 발생하거나 요소가 누락될 수 있습니다.
#### ✨고친점
- 리스트의 요소를 삭제하면서 반복문을 사용하면 얻고자하는 결과를 얻기 어려우므로, 삭제 목록에 포함되지 않은 요소만 리스트에 요소를 추가하는 방식을 사용하였습니다. 
