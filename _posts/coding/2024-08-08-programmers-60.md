---
layout: single
title: "프로그래머스 - 카드 뭉치"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/159994)  

## 📌 카드 뭉치

#### 📖 문제 설명 :  
코니는 영어 단어가 적힌 카드 뭉치 두 개를 선물로 받았습니다. 코니는 다음과 같은 규칙으로 카드에 적힌 단어들을 사용해 원하는 순서의 단어 배열을 만들 수 있는지 알고 싶습니다.

- 원하는 카드 뭉치에서 카드를 순서대로 한 장씩 사용합니다.
- 한 번 사용한 카드는 다시 사용할 수 없습니다.
- 카드를 사용하지 않고 다음 카드로 넘어갈 수 없습니다.
- 기존에 주어진 카드 뭉치의 단어 순서는 바꿀 수 없습니다.

예를 들어 첫 번째 카드 뭉치에 순서대로 ["i", "drink", "water"], 두 번째 카드 뭉치에 순서대로 ["want", "to"]가 적혀있을 때 ["i", "want", "to", "drink", "water"] 순서의 단어 배열을 만들려고 한다면 첫 번째 카드 뭉치에서 "i"를 사용한 후 두 번째 카드 뭉치에서 "want"와 "to"를 사용하고 첫 번째 카드뭉치에 "drink"와 "water"를 차례대로 사용하면 원하는 순서의 단어 배열을 만들 수 있습니다.

문자열로 이루어진 배열 cards1, cards2와 원하는 단어 배열 goal이 매개변수로 주어질 때, cards1과 cards2에 적힌 단어들로 goal를 만들 있다면 "Yes"를, 만들 수 없다면 "No"를 return하는 solution 함수를 완성해주세요.

#### 📖 제한사항 :  
- 1 ≤ cards1의 길이, cards2의 길이 ≤ 10
  - 1 ≤ cards1[i]의 길이, cards2[i]의 길이 ≤ 10
  - cards1과 cards2에는 서로 다른 단어만 존재합니다.
- 2 ≤ goal의 길이 ≤ cards1의 길이 + cards2의 길이
  - 1 ≤ goal[i]의 길이 ≤ 10
  - goal의 원소는 cards1과 cards2의 원소들로만 이루어져 있습니다.
- cards1, cards2, goal의 문자열들은 모두 알파벳 소문자로만 이루어져 있습니다.

#### 📖 입출력 예 : 

|name|yearing|photo|result|
|---|---|---|----|
|["i", "drink", "water"]|["want", "to"]|["i", "want", "to", "drink", "water"]|"Yes"|
|["i", "water", "drink"]|["want", "to"]|["i", "want", "to", "drink", "water"]|"No"|

#### 📖 입출력 예 설명 : 
입출력 예 #2

cards1에서 "i"를 사용하고 cards2에서 "want"와 "to"를 사용하여 "i want to"까지는 만들 수 있지만 "water"가 "drink"보다 먼저 사용되어야 하기 때문에 해당 문장을 완성시킬 수 없습니다. 따라서 "No"를 반환합니다.

#### 😅 오류 코드
```python
def solution(cards1, cards2, goal):
    answer = "Yes"
    card = cards1 + cards2

    for i in card:
        if i in goal:
            goal.pop(0)
        else:
            answer = "No"

    return answer
```
card1과 card2를 합쳐 card변수에 넣어주고 goal과 비교해 없으면 "No"를 반환해주는 코드를 작성하려고 했다. 
답이 다르게 나와 문제를 다시 읽어보니 카드에 적힌 단어 순서대로 goal배열을 만들 수 있는지 문제였기 때문에 저런 방식으로 문제를 풀면 
안된다는 것을 깨달았다. 

#### ✏️ 정답 코드  
```python
def solution(cards1, cards2, goal):
    answer = "Yes"
    
    for i in goal:
        if i in cards1: # cards1에 있는 경우
            if i == cards1[0]: # 젤 앞에 값과 같으면 
                cards1.pop(0) # cards1에서 삭제
            else: # 다르면
                answer = "No" # "No" 반환 후 종료
                break
        elif i in cards2: # cards2에 있는 경우
            if i == cards2[0]:
                cards2.pop(0)
            else:
                answer = "No"
                break

    return answer
```
각각의 카드뭉치에 있는 순서대로 goal에 적혀있다면 "Yes"를 반환하는 문제이다. 
(cards1과 cards2를 번갈아가며 단어를 사용하는 것은 괜찮지만, cards1의 1번째 문자가 나오고 cards1의 0번째 문자가 나오게된다면 "No"반환)  
goal을 반복하며 cards1의 0번째 값과 같다면 cards1에서 0번째문자를 삭제하고, 같지 않다면 "No"를 반환하도록 코드를 작성했다. 
card2[0]과 같을 때도 똑같이 수행하도록 코드를 작성햤다. 

#### ✨ 느낀점 
- 첫번째로 작성한 코드가 내가 생각했던 것과 다른 결과가 도출되어 조금 당황했었다.
  문제를 잘못 읽은 점도 있었지만, 코드를 짧게 작성하고 간단하게 작성하려고 생각하다보니,
  자꾸 오류가 생기는 거 같다. 코드가 길더라도 일단 작성하고 실행이 됐을 경우, 그때 코드를 간결하게 하는 방법을
  연구해야겠다. 




