---
layout: single
title: "프로그래머스 - 가장 가까운 같은 글자"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/142086)  

## 📌가장 가까운 같은 글자

#### 📖문제 설명 :  
![image](https://github.com/user-attachments/assets/e2cf0302-3198-4d17-8f16-4da10ef1baa6)

#### 📖제한 사항 :  
- 1 ≤ s의 길이 ≤ 10,000
  - s은 영어 소문자로만 이루어져 있습니다.
  
#### 📖입출력 예 : 

|s|return|
|---|---|
|"banana"|[-1, -1, -1, 2, 2, 2]|
|"foobar"|[-1, -1, 1, -1, -1, -1]|

#### ✏️정답 코드
```python
def solution(s):
    answer = []
    a = ''
    old = 0
    
    for i in range(len(s)): 
        if s[i] not in a: # a라는 문자열로 선언된 변수에 현재값인 s[i]가 없다면
           a += s[i] # a를 넣어줌
           answer += [-1] # 처음 나온 문자이므로 answer에는 -1을 넣어줘야함
        else: # s[i]가 a에 있다면
            old = a.rfind(s[i]) # 현재 자신과 가장 가까운 곳에 있는 글자의 인덱스 값을 알아야하므로 rfind()함수 사용
            a +=(s[i]) # 가까운 곳에 있는 글자의 인덱스 값을 찾은 후, a에 문자 넣어줌
            answer += [i - old] # answer에는 현재 인덱스값에서 자신과 같으면서 가까이 있는 글자의 인덱스값(old)를 빼준 값을 넣어줌
    return answer
```


<br>

#### ✨코드설명
- 먼저 처음 나온 문자는 앞에 같은 글자가 없으므로 a라는 문자열 변수를 주어 현재 값인 s[i]를 a에 넣어주고 answer에 -1을 넣어주는 코드를 작성했다.
  그러고 나서 이제 자신의 앞에 같은 글자가 있는 경우를 생각해봤다. 현재 인덱스 값과 자신의 앞에 똑같은 글자의 인덱스 값을 구해서 빼주어야하므로,
  a에 문자를 넣어주기전에 마지막으로 들어온 자신과 똑같은 문자의 인덱스 값을 구해줘야한다. old라는 변수를 주어 rfind()함수를 사용해 인덱스 값을 쉽게 구할 수 있었다.
  인덱스값을 구해준 후, a에 문자를 넣어주는 이유는 먼저 문자를 넣고 rfind()를 해주면 방금 넣은 문자의 인덱스 값을 반환해주기 때문이다.
  a에 문자를 넣어주고 answer에는 현재 인덱스인 i에서 old를 빼주면 몇 칸 앞에 자신과 같은 문자가 있는지 알 수 있다. 

