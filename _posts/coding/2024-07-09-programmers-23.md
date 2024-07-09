---
layout: single
title: "프로그래머스 - 2의 영역"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181894)  

## 📌2의 영역
#### 📖문제 설명 :  
정수 배열 arr가 주어집니다. 배열 안의 2가 모두 포함된 가장 작은 연속된 부분 배열을 return 하는 solution 함수를 완성해 주세요. 
단, arr에 2가 없는 경우 [-1]을 return 합니다.

#### 입출력 예  
|arr|result|
|---|---|
|[1, 2, 1, 4, 5, 2, 9]|[2, 1, 4, 5, 2]|
|[1, 2, 1]|[2]|
|[1, 1, 1]|[-1]|
|[1, 2, 1, 2, 1, 10, 2, 1]|[2, 1, 2, 1, 10, 2]|

<br>

#### ✏️정답 코드
```python
def solution(arr):
    answer = []
    
    if 2 in arr:
        if arr.count(2) > 1:
            start = arr[:].index(2)
            end = len(arr) - arr[::-1].index(2)
        else:
            answer = [arr[arr.index(2)]]
            return answer
    else:
        return [-1]

    print(start, end)

    answer = arr[start:end]
    return answer
```

<br>

#### ✨코드 설명
- arr 안에 2가 1개 이상이면 첫번째 2가 위치한 인덱스위 끝에 위치한 2의 인덱스를 구해 그 사이 값들을 반환해주고,
  한개라면 그 자리 인덱스 값을 반환하고, 없다면 -1을 넣어준다.  
  마지막에 위치한 2의 인덱스를 구할 때, 전체 길이에서 마지막 2위치 인덱스 값을 빼주는 이유는 역순으로 순서를 바꿔 마지막 원소 인덱스가
  0부터 시작하기 때문에 전체 길이에서 빼줘야 찾는 문자의 마지막 인덱스 값이 되기 때문이다. 
  
#### ✨느낀점
- index함수를 사용해야겠다는 생각이 들었는데 어떻게 구현하면 좋을지 생각이 잘 안나서 다른 사람들의 코드를 보고 참고하였다.
  end = arr[::-1].index(2) 이렇게 해주면 될줄알았는데, end = len(arr) - arr[::-1].index(2) 이렇게 해야 답이 나와 처음에는 왜 이렇게 해야하는지 이해가 안갔는데
  다른사람들의 설명도 보고 구글링하며 이해할 수 있었다. 
