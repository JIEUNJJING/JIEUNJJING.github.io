---
layout: single
title: "프로그래머스 - K번째수"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/42748)  

## 📌K번째수

#### 📖문제 설명 :  
![image](https://github.com/user-attachments/assets/e6796fd9-4ab3-455f-8280-5b5131910fbc)

#### 📖제한 사항 :  
- array의 길이는 1 이상 100 이하입니다.
- array의 각 원소는 1 이상 100 이하입니다.
- commands의 길이는 1 이상 50 이하입니다.
- commands의 각 원소는 길이가 3입니다.
  
#### 📖입출력 예 : 

|A|B|result|
|---|---|---|
|[1, 5, 2, 6, 3, 7, 4]|[[2, 5, 3], [4, 4, 1], [1, 7, 3]]|[5, 6, 3]|

#### 😅 오류 코드  
```python
def solution(array, commands):
    answer = []
    a = []

    for i, j , k in commands: 
        a.append(array[i - 1:j]) 
        a.sort()
        answer.append(a[k - 1])
    
    return answer
```
answer.append(a[k - 1]) 여기 이 부분에서 자꾸 IndexError: list index out of range 이 오류가 발생했다. 
print(k - 1)을 했을 땐 2, 0, 2 이렇게 잘 나왔는데 왜 오류가 뜨는지 이해를 못했다. 
계속 코드를 보다보니 a가 리스트 형태라 array의 슬라이스된 리스트를 a에 넣어주어 a리스트 안에 리스트 형태로 원소들이 들어가는데, 
이때, 정렬하면 슬라이싱된 리스트 안 원소가 정렬되는게 아니라 a안에 리스트를 정렬하게 된다. // [[1, 5, 2, 6, 3, 7, 4], [5, 2, 6, 3], [6]] 
여기서 answer.append(a[k - 1]) 이 코드를 하려고하니 인덱스 범위 오류가 난 것이였다. 

#### ✏️ 정답 코드  
```python
def solution(array, commands):
    answer = []
    a = 0

    for i, j , k in commands: # 각각 i, j, k로 세개의 숫자를 받아옴
        a = 0 # a초기화
        a = array[i - 1:j] # a변수를 지정해주어 i번째부터 j번째 숫자까지 자름
        a.sort() # 숫자를 정렬해줌
        answer.append(a[k - 1]) # 정렬된 숫자의 k번째 수를 answer에 넣어줌
    
    return answer
```
제일 먼저 a를 초기화해주고, 슬라이싱한 값을 a 변수에 넣어주었다. 그럼 [5, 2, 6, 3]이 들어가게되는데 여기서 정렬을 해주면 [2, 3, 5, 6]이 a에 들어가게된다. 
정렬해준 후, append()를 사용해 a의 k번째 값을 answer에 넣어주는 코드를 작성했다. 

#### ✨ 느낀점 
- 자꾸 똑같은 오류가 떠서 왜 이런 오류가 나는지 정말 많이 고민하고 코드를 계속 분석했다.
  다른 사람들의 코드를 참고하려하다 마지막으로 한 번 더 봤는데 오류를 발견하고 고쳐서 너무 뿌듯했다.
  내가 생각했던 것과 다르게 코드가 돌아가고 있어서 났던 오류라 고치는건 수월했지만, 오류를 찾아내는데 많은 시간을 썼던 거 같다.
  한 번 경험해봤으니 이젠 이런 실수는 하지 않을 거 같다! 비슷한 실수를 하더라도 쉽게 찾아낼 수 있을 거 같다. 

  
