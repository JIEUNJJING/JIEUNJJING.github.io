---
layout: single
title: "프로그래머스 - 2차원으로 만들기"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120842#)  

## 📌2차원으로 만들기
#### 📖문제 설명 :  
정수 배열 num_list와 정수 n이 매개변수로 주어집니다. num_list를 다음 설명과 같이 2차원 배열로 바꿔 return하도록 solution 함수를 완성해주세요.

num_list가 [1, 2, 3, 4, 5, 6, 7, 8] 로 길이가 8이고 n이 2이므로 num_list를 2 * 4 배열로 다음과 같이 변경합니다. 2차원으로 바꿀 때에는 num_list의 원소들을 앞에서부터 n개씩 나눠 2차원 배열로 변경합니다.

#### 입출력 예  

|num_list|n|result|
|---|---|---|
|[1, 2, 3, 4, 5, 6, 7, 8]|2|[[1, 2], [3, 4], [5, 6], [7, 8]]|

<br>

#### ✏️내 코드
```python
def solution(num_list, n):
    answer = []

    for i in range(0, len(num_list), n):
        answer.append(num_list[i:i+n])

    return answer
```


<br>

#### ✨구현 방법 
- i가 0부터 len(num_list)까지 n 간격으로 증가하는 반복문을 실행하여, i부터 i+n까지 슬라이싱한 값을 answer에 넣어준다.
  기본 주어진 코드에는 answer = [[]] 이렇게 정의되어있는데, 이 상태로 실행하면 제일 앞에 [] 이런 빈 리스트가 포함되므로,
  answer = []이렇게 코드를 바꿔 실행시켰다. 
  
#### ✨느낀점
- 이 문제를 어떻게 풀지 감이 안잡혀서 다른 사람들의 질문들과 코드를 보고 참고하여 작성하였다.
  이번에는 참고해서 풀었으니, 다음에 이런 비슷한 문제가 나오면 스스로 해결해봐야겠다.  
  
  
