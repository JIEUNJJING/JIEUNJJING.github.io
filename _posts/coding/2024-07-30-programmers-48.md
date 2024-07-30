---
layout: single
title: "프로그래머스 - 행렬의 덧셈"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12950)  

## 📌행렬의 덧셈

#### 📖문제 설명 :  
행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

#### 📖제한 사항 :  
- 행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

  
#### 📖입출력 예 : 

|arr1|arr2|return|
|---|---|---|
|[[1,2],[2,3]]|[[3,4],[5,6]]|[[4,6],[7,9]]|
|[[1],[2]]|[[3],[4]]|[[4],[6]]|

#### ✏️나의 코드
```python
def solution(arr1, arr2):
    answer = []

    for i in range(len(arr1)):
        sum = []
        for j in range(len(arr1[0])):
            sum.append(arr1[i][j] + arr2[i][j])
        answer.append(sum)

    return answer
```

#### ✏️다른 사람 코드
```python
def sumMatrix(A,B):
    for i in range(len(A)):
        for j in range(len(A[0])):
            A[i][j] += B[i][j]

    return A
```

<br>

#### ✨코드설명
- 나는 sum이라는 배열을 만들어 더한값을 answer에 다시 넣어주었는데, 다른 사람의 코드를 보니 꼭 answer에 넣지 않고 arr1 배열에 arr2를 더해주어 arr1을 반환해도 되는
  문제였다. arr1의 원소가 바뀌지만, 다시 접근할 일이 없어서 된다고 했다. 이런 코드를 생각하다니.. 대단한 거 같다.
  다른 사람들의 코드를 보며 나도 더 성장해야겠다. 
