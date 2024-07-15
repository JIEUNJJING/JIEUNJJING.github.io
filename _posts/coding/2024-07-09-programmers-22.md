---
layout: single
title: "프로그래머스 - 영어가 싫어요"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120894)  

## 📌영어가 싫어요
#### 📖문제 설명 :  
영어가 싫은 머쓱이는 영어로 표기되어있는 숫자를 수로 바꾸려고 합니다. 문자열 numbers가 매개변수로 주어질 때, numbers를 정수로 바꿔 return 하도록 solution 함수를 완성해 주세요.

#### 입출력 예 

|numbers|result|
|---|---|
|"onetwothreefourfivesixseveneightnine"|123456789|
|"onefourzerosixseven"|14067|

<br>

#### ✏️정답 코드
```python
def solution(numbers):
    answer = 0
    dict = {'zero':'0', 'one':'1', 'two':'2', 'three':'3', 'four':'4', 
            'five':'5', 'six':'6', 'seven':'7', 'eight':'8', 'nine':'9'}
    for i in dict.keys():
        numbers = numbers.replace(i, dict[i])
    answer = int(numbers)
    return answer
```

<br>

#### ✨코드 설명
- 이 문제에서 딕셔너리 개념을 사용하였다. 반복문을 돌며 딕셔너리 안에 있는 key값과 같다면 그 key값의 value로 대체해
  문자대신 숫자로 대체되도록 코드를 작성하였다. 그리고 문자열로 데이터 타입이 지정되어 있어 정수형으로 마지막 부분에서 바꿔주었다. 
  
#### ✨느낀점
- 딕셔너리를 사용해야한다는 생각은 들었지만, 그 다음 어떻게 코드를 짜야할지 생각하는데 시간이 조금 걸렸다.
  for문 적는 부분에서 조금 생각을 많이 했고, 다른 부분은 많이 사용해본 문법이라 쉽게 사용할 수 있었다. 
  
