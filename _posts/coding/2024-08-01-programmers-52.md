---
layout: single
title: "프로그래머스 - 숫자 문자열과 영단어"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/81301)  

## 📌숫자 문자열과 영단어

#### 📖문제 설명 :  
![image](https://github.com/user-attachments/assets/a65b9f2c-5847-4439-8e2f-2319c347bd71)

![image](https://github.com/user-attachments/assets/2bd3dbac-9580-4ee8-abc4-29b0efa394ae)


#### 📖제한 사항 :  
- 1 ≤ s의 길이 ≤ 50
- s가 "zero" 또는 "0"으로 시작하는 경우는 주어지지 않습니다.
- return 값이 1 이상 2,000,000,000 이하의 정수가 되는 올바른 입력만 s로 주어집니다.
  
#### 📖입출력 예 : 

|s|result|
|---|---|
|"one4seveneight"|1478|
|"23four5six7"|234567|
|"2three45sixseven"|234567|
|"123"|123|

#### 😅 첫 번째 오류
```python
def solution(s):
    answer = []
    dic = {0:'zero', 1 : 'one', 2:'two', 3:'three', 4:'four', 5:'five', 6:'six', 7:'seven', 8:'eight', 9:'nine'}

    for i in s:
        if i.isdigit():
            answer += i
        else:
            if i == dic.values():
                print(i)
                answer += dic.keys()

    return answer
```
첫번째 생각한 방법 : 숫자는 그대로 넣어주고 문자가 나왔을 경우 dic의 values와 비교했을 때 같다면 value의 key값을 넣어주는 코드를 작성했다.
숫자는 잘 들어갔지만, 문자가 나올때 잘 들어가지않음 아마 i가 한 문자씩 비교하게되는데 value는 'one'이런식으로 들어가 비교하기 때문에 안맞아서 그런 거 같다. 

#### 😅 두 번째 오류
```python
def solution(s):
    answer = ''
    dic = {0:'zero', 1 : 'one', 2:'two', 3:'three', 4:'four', 5:'five', 6:'six', 7:'seven', 8:'eight', 9:'nine'}
    for i in s:
        if i.isdigit():
            answer += i
    for k, v in dic.items():
        if v in s:
            answer += str(k)
    return int(answer)
```
숫자로 변환되어 출력은 잘 됐지만 순서가 다르게 나왔다. 원래 출력 결과 : 1478 이 코드 출력 : 4178

#### ✏️ 정답 코드  
```python
def solution(s):
    answer = ''
    dic = {0:'zero', 1 : 'one', 2:'two', 3:'three', 4:'four', 5:'five', 6:'six', 7:'seven', 8:'eight', 9:'nine'}
    
    for k, v in dic.items(): # for문을 반복하며 k,v로 각각 key,value값을 받아옴
        s = s.replace(v, str(k)) # s문자열에서 v를 찾아 k로 대체해줌
    answer = int(s)
    
    return answer
```
고민하다 다른 사람들의 코드를 보는데 replace함수를 사용하시는걸 보고 깨달았다.
replace함수는 값을 대체해주기때문에 가능한 것을 ... 
replace함수를 사용했더니 실행이 되었다. 처음 생각한 코드보다 훨씬 짧고 쉽게 해결할 수 있었다. 

#### ✨느낀점 
- 코드를 작성하며 정답과 다르게 나와 여러가지 방법을 생각해보며 시도하니 코드를 읽는 실력도 점점 더 성장하는 거 같다.
  다른 사람의 코드를 보고 힌트를 얻었지만, 다른 사람의 코드를 분석하고 이해하는 것도 하나의 공부라고 생각하며 코딩 실력을 기르는데
  도움이 될 것이라 생각한다. 그리고 이렇게 내가 겪은 오류와 코드를 분석하고 적으니 오류에 대한 이해도 더 잘 되는 거 같다.
  내가 겪은 오류와 해결 과정을 기록한 것이 다른 사람들에게 도움이 되었으면 한다. 
