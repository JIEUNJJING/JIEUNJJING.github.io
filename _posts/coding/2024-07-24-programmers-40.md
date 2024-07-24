---
layout: single
title: "프로그래머스 - 로그인 성공?"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/120883)  

## 📌로그인 성공?
#### 📖문제 설명 :  
![image](https://github.com/user-attachments/assets/e80b1de1-de80-4ce4-b5a6-99fc7a289ac6)

#### 📖제한 사항 :  
![image](https://github.com/user-attachments/assets/e4d1576f-a39a-4023-8a18-f864c4c2a455)

#### 📖입출력 예 : 
|id_pw|db|result|
|---|---|---|
|["meosseugi", "1234"]|[["rardss", "123"], ["yyoom", "1234"], ["meosseugi", "1234"]]|"login"|
|["programmer01", "15789"]|[["programmer02", "111111"], ["programmer00", "134"], ["programmer01", "1145"]]|"wrong pw"|
|["rabbit04", "98761"]|[["jaja11", "98761"], ["krong0313", "29440"], ["rabbit00", "111333"]]|"fail"|

#### 📖입출력 예 설명 : 
![image](https://github.com/user-attachments/assets/544538a1-fde6-4075-a954-7ad0acf09a01)

#### ✏️오류 코드 
```python
def solution(id_pw, db):
    answer = ''

    for i in db:
        if i[0] == id_pw[0] and i[1] == id_pw[1]:
            return 'login'
        elif i[0] == id_pw[0] and i[1] != id_pw[1]:
            return 'wrong pw'
        elif i[0] != id_pw[0]: # 오류 
            return 'fail'
    return answer
```

#### ✏️정답 코드
```python
def solution(id_pw, db):
    answer = ''

    for i in db:
        if i[0] == id_pw[0] and i[1] == id_pw[1]:
            return 'login'
        elif i[0] == id_pw[0] and i[1] != id_pw[1]:
            return 'wrong pw'
    return 'fail'
```

<br>

#### ✨코드설명
- 처음에 코드 작성할 떄, 아이디가 다르다면 fail을 반환하는 코드를 작성했는데, 저렇게 조건을 준다면 아이디가 다른 예시가 처음 나왔을 때
  바로 fail을 반환하게 된다. 주어진 예시를 다 돌고 난 후에 아이디가 일치하는 회원이 없다면 fail을 반환해야하므로
  login과 wrong pw를 반환하는 조건문을 작성한 후 return 값을 fail로 주면 된다. 아니면 answer 값을 fail로 초기화해주고,
  login이나 wrong pw로 answer 값을 바꿔주는 코드를 작성해도 무관하다.  
  
