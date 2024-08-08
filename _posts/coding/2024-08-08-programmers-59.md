---
layout: single
title: "프로그래머스 - 추억 점수"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/176963)  

## 📌 추억 점수

#### 📖 문제 설명 :  
사진들을 보며 추억에 젖어 있던 루는 사진별로 추억 점수를 매길려고 합니다. 사진 속에 나오는 인물의 그리움 점수를 모두 합산한 값이 해당 사진의 추억 점수가 됩니다. 예를 들어 사진 속 인물의 이름이 ["may", "kein", "kain"]이고 각 인물의 그리움 점수가 [5점, 10점, 1점]일 때 해당 사진의 추억 점수는 16(5 + 10 + 1)점이 됩니다. 다른 사진 속 인물의 이름이 ["kali", "mari", "don", "tony"]이고 ["kali", "mari", "don"]의 그리움 점수가 각각 [11점, 1점, 55점]]이고, "tony"는 그리움 점수가 없을 때, 이 사진의 추억 점수는 3명의 그리움 점수를 합한 67(11 + 1 + 55)점입니다.

그리워하는 사람의 이름을 담은 문자열 배열 name, 각 사람별 그리움 점수를 담은 정수 배열 yearning, 각 사진에 찍힌 인물의 이름을 담은 이차원 문자열 배열 photo가 매개변수로 주어질 때, 사진들의 추억 점수를 photo에 주어진 순서대로 배열에 담아 return하는 solution 함수를 완성해주세요.

#### 📖 제한사항 :  
- 3 ≤ name의 길이 = yearning의 길이≤ 100
  - 3 ≤ name의 원소의 길이 ≤ 7
  - name의 원소들은 알파벳 소문자로만 이루어져 있습니다.
  - name에는 중복된 값이 들어가지 않습니다.
  - 1 ≤ yearning[i] ≤ 100
  - yearning[i]는 i번째 사람의 그리움 점수입니다.
- 3 ≤ photo의 길이 ≤ 100
  - 1 ≤ photo[i]의 길이 ≤ 100
  - 3 ≤ photo[i]의 원소(문자열)의 길이 ≤ 7
  - photo[i]의 원소들은 알파벳 소문자로만 이루어져 있습니다.
  - photo[i]의 원소들은 중복된 값이 들어가지 않습니다.배열의 각 원소 x를 이진수로 변환했을 때의 길이는 n 이하이다. 즉, 0 ≦ x ≦ 2n - 1을 만족한다.

#### 📖 입출력 예 : 

|name|yearing|photo|result|
|---|---|---|----|
|["may", "kein", "kain", "radi"]|[5, 10, 1, 3]|[["may", "kein", "kain", "radi"],["may", "kein", "brin", "deny"], ["kon", "kain", "may", "coni"]]|[19, 15, 6]|
["kali", "mari", "don"]|[11, 1, 55]|[["kali", "mari", "don"], ["pony", "tom", "teddy"], ["con", "mona", "don"]]|[67, 0, 55]|
["may", "kein", "kain", "radi"]|[5, 10, 1, 3]|[["may"],["kein", "deny", "may"], ["kon", "coni"]]|[5, 15, 0]|

#### 😅 고민했던 부분
이 문제를 처음 읽었을 때, 바로 딕셔너리를 사용해야겠다는 생각이 들었다. 
문제는 어떻게 딕셔너리 형태로 바꿀 것인지 생각하는 것이었다. 생각해낸 방법은 for문을 사용해 딕셔너리를 만드는 것이였다. 

```python
def solution(name, yearning, photo):
    answer = []
    dic = {}

    for i in name:
        for j in yearning:
            dic[i] = j
    print(dic)

    return answer
```
이렇게 코드를 작성하고 테스트를 해보았더니, {'may': 3, 'kein': 3, 'kain': 3, 'radi': 3}이렇게 value값이 잘 들어가지 않았다. 
딕셔너리에 매핑할 때 이중 for문을 사용해 yearing의 값을 각 name에 반복적으로 값이 할당되어 마지막 값만 들어간 것이다. 
그러다 내가 공부한 파이썬 함수를 보았는데, zip()함수가 그제서야 생각이 났다. 
아직 익숙하지 않아 생각이 안 났던 거 같다. 

#### ✏️ 정답 코드  
```python
def solution(name, yearning, photo):
    answer = []
    dic = {}

    dic = dict(zip(name, yearning)) # 딕셔너리로 묶어줌

    for i in photo: 
        sum = 0 # 총 합 초기화(각각의 사진의 합을 구해야하므로)
        for j in i:
            if j in dic:
                sum += dic[j] # 각 key값에 대응되는 값을 더해줌
        answer.append(sum)

    return answer
```
zip함수를 사용한 결과 쉽게 딕셔너리로 매핑할 수 있었다. 
사진 하나하나를 반복하며 사진속에 있는 사람 한명에 대응하는 값들을 sum변수에 더해주었다. 
그리고 다음 사진의 그리움 점수를 더하기 위해 두번째 반복문을돌고 총 합계를 answer에 넣어준 후, 
sum을 초기화해주고 다시 합을 계산해 주었다. 이 과정을 photo 수 만큼 반복한다. 

#### ✨ 느낀점 
- 많이 사용했던 파이썬 함수는 바로 생각이 나지만 ,
  아직 많이 사용해보지 않았던 함수들은 생각이 잘 나지않았다. 유용하게 함수를 잘 사용할 수 있도록 되도록이면
  다양한 함수를 사용하려고 노력해야겠다. 딕셔너리 개념은 알지만, 사용하는데에는 실력이 아직 미숙하다는 것을 느꼈다. 
  
