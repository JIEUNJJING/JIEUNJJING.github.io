---
layout: single
title: "프로그래머스 - 시저 암호"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/12926)  

## 📌시저 암호

#### 📖문제 설명 :  
어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 됩니다. "z"는 1만큼 밀면 "a"가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.

#### 📖제한 사항 :  
- 공백은 아무리 밀어도 공백입니다.
- s는 알파벳 소문자, 대문자, 공백으로만 이루어져 있습니다.
- s의 길이는 8000이하입니다.
- n은 1 이상, 25이하인 자연수입니다.
  
#### 📖입출력 예 : 

|s|n|return|
|---|---|---|
|"AB"|1|"BC"|
|"z"|1|"a"|
|"a B z"|4|"e F d"|

#### ✏️정답 코드
```python
def solution(s, n):
    answer = ''

    for i in s:
        if i == ' ': # 공백일 경우
            answer += ' ' # 그대로 공백 넣어줌
        else:
            if 'a' <= i <= 'z':
                if ord(i) + n <= ord('z'): # n을 더해줬을 때, z보다 작거나 같으면 
                    answer += chr(ord(i) + n) # n을 더해주고
                else: # z보다 커서 범위를 넘어간다면 
                    answer += chr(ord(i) - 26 + n) # 현재 ord(i)에 26을 빼준 후, n을 더해준다
            elif 'A' <= i <= 'Z':
                if ord(i) + n <= ord('Z'):
                    answer += chr(ord(i) + n)
                else:
                    answer += chr(ord(i) - 26 + n)
    return answer
```


<br>

#### ✨코드설명
- 주어진 문자열 s를 반복하며, 먼저 공백인지 구분을 해준다. 공백이라면 answer에 그대로 공백을 추가해주면 된다.
  그리고 a와 z사이 문자이고 ord(i)에 n을 더했을 때, z보다 작거나 같다면 별 다른 연산없이 ord(i) + n 을 해주면된다.
  만약 ord(i) + n을 했는데 ord('z')보다 커 범위를 벗어날 경우, 다시 a로 가서 연산을 해야하므로 ord(i) - 26 + n과 같이 빼기 연산을 추가해줘야 한다.
  대문자의 경우도 소문자와 마찬가지로 코드를 작성해주면 된다. 아스키코드 표를 참고하며 코드를 작성하면 쉽게 풀 수 있다. 



