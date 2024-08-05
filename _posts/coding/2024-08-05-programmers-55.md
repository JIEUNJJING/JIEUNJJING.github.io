---
layout: single
title: "프로그래머스 - 문자열 내 마음대로 정렬하기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12915)  

## 📌문자열 내 마음대로 정렬하기

#### 📖문제 설명 :  
문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 예를 들어 strings가 ["sun", "bed", "car"]이고 n이 1이면 각 단어의 인덱스 1의 문자 "u", "e", "a"로 strings를 정렬합니다.

#### 📖제한 사항 :  
- strings는 길이 1 이상, 50이하인 배열입니다.
- strings의 원소는 소문자 알파벳으로 이루어져 있습니다.
- strings의 원소는 길이 1 이상, 100이하인 문자열입니다.
- 모든 strings의 원소의 길이는 n보다 큽니다.
- 인덱스 1의 문자가 같은 문자열이 여럿 일 경우, 사전순으로 앞선 문자열이 앞쪽에 위치합니다.
  
#### 📖입출력 예 : 

|strings|n|result|
|---|---|---|
|["sun", "bed", "car"]|1|["car", "bed", "sun"]|
|["abce", "abcd", "cdx"]|2|["abcd", "abce", "cdx"]|

#### 😅 오류 코드  
```python
def solution(strings, n):
    answer = []

    new = sorted(strings)
    for i in range(len(new)):
        for j in range(i + 1, len(new)):
            if new[i][n] > new[j][n]: # 앞에 문자가 더 클 경우
                new[i] ,new[j] = new[j], new[i] # 자리 바꿈
                
    answer = strings
    return answer
```
처음에 코드를 작성할 때, 먼저 사전순으로 정렬하고 n번째 위치값으로 정렬하는 코드를 작성했다. 
이 코드를 작성했을 때, solution(["aea", "ba", "ce", "aee"], 1)이러한 값을 넣었더니 섞인 값이 나왔다. 
뭐가 잘못된건지 잘 모르겠어서 다른 사람에게 물어봤더니 제일 먼저 정렬하고 n번째 위치값으로 다시 정렬해 사전순으로 정렬한 값이 섞여버려서 
이러한 결과가 나온다고 했다. 그래서 선택정렬이 아닌 삽입정렬을 사용해보라는 피드백을 바탕으로 다시 코드를 작성했다. 


#### ✏️ 정답 코드  
```python
def solution(strings, n):
    answer = []
    j = 0

    new_s = sorted(strings) # sorted() 함수는 정렬된 새로운 리스트를 반환

    #삽입정렬(Insertion Sort)
    for i in range(1, len(new_s)):
        j = i
        while new_s[j-1][n] > new_s[j][n] and j > 0:
            new_s[j], new_s[j-1] = new_s[j-1], new_s[j] # 앞자리와 swap 
            j = j - 1

    answer = new_s
    return answer
```

#### ✨코드 분석 & 느낀점 
- 먼저 string을 정렬한 값을 new_s에 넣어주고, 반복문을 돌게된다.
  이때 j는 i로 설정해주고 앞에 자리의 n번째 문자가 현재 자리의 n번째 문자보다 크고 j값이 0보다 크다면 계속 while문을 반복한다.
  이렇게 조건을 준 이유는 선택정렬이 현재 요소와 그 앞의 요소를 비교하며 더 작은 것을 앞으로 자리를 바꿔주는 알고리즘이기 때문입니다.
  j = j - 1해준 이유는 i가 1부터 시작하기 때문에 올바른 위치로 이동시켜주기위해 작성한 코드다. 


  
