---
layout: single
title: "프로그래머스 - 그림 확대"
categories: 
  - coding
tag:
  - [python, coding, grammar]
--- 
[문제링크](https://school.programmers.co.kr/learn/courses/30/lessons/181836)  

## 📌그림 확대

#### 📖문제 설명 :  
직사각형 형태의 그림 파일이 있고, 이 그림 파일은 1 × 1 크기의 정사각형 크기의 픽셀로 이루어져 있습니다. 이 그림 파일을 나타낸 문자열 배열 picture과 정수 k가 매개변수로 주어질 때, 이 그림 파일을 가로 세로로 k배 늘린 그림 파일을 나타내도록 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

#### 📖제한 사항 :  
- 1 ≤ picture의 길이 ≤ 20
- 1 ≤ picture의 원소의 길이 ≤ 20
- 모든 picture의 원소의 길이는 같습니다.
- picture의 원소는 '.'과 'x'로 이루어져 있습니다.
- 1 ≤ k ≤ 10
  
#### 📖입출력 예 : 

|picture|k|result|
|---|---|---|
|[".xx...xx.", "x..x.x..x", "x...x...x", ".x.....x.", "..x...x..", "...x.x...", "....x...."]|2|["..xxxx......xxxx..", "..xxxx......xxxx..", "xx....xx..xx....xx", "xx....xx..xx....xx", "xx......xx......xx", "xx......xx......xx", "..xx..........xx..", "..xx..........xx..", "....xx......xx....", "....xx......xx....", "......xx..xx......", "......xx..xx......", "........xx........", "........xx........"]|
|["x.x", ".x.", "x.x"]|3|["xxx...xxx", "xxx...xxx", "xxx...xxx", "...xxx...", "...xxx...", "...xxx...", "xxx...xxx", "xxx...xxx", "xxx...xxx"]|

#### 📖입출력 예 설명 : 
![image](https://github.com/user-attachments/assets/eea9150b-c002-4014-ae0e-476d9c8c38b9)

![image](https://github.com/user-attachments/assets/0ccde5cf-fcfa-4d81-b591-a55049414e9d)

#### ✏️정답 코드
```python
def solution(picture, k):
    answer = []
    expand_str = ''
    
    for p1 in picture: 
        expand_str = '' 
        for p2 in p1: 
            for e in range(k): 
                expand_str += p2 
        for e in range(k): 
            answer.append(expand_str)

    return answer
```

<br>

#### ✨코드설명
- for문으로 각 좌표의 픽셀정보를 가져와서 해당 픽셀을 for문에서 k배수만큼 반복하며 expand_str 변수에 더해주어 픽셀을 늘려준다.
  이렇게 첫번째 요소의 모든 픽셀정보를 k배수 만큼 늘렸으면 세로길이도 늘려야 함으로 for문으로 k배수 만큼 반복하면서 expand_str 값을 answer 리스트 변수에 추가해준다.
  
  
