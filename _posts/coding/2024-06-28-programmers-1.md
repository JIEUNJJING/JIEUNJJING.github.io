---
layout: single
title: "첫 포스팅 입니다!"
categories: 
  - coding
tag:
  - python
--- 
[프로그래머스 꼬리 문자열 링](https://school.programmers.co.kr/learn/courses/30/lessons/181841)  

## :pushpin:꼬리 문자열
#### :book:문제 설명 :  
문자열들이 담긴 리스트가 주어졌을 때, 모든 문자열들을 순서대로 합친 문자열을 꼬리 문자열이라고 합니다.  
꼬리 문자열을 만들 때 특정 문자열을 포함한 문자열은 제외시키려고 합니다. 예를 들어 문자열 리스트 ["abc", "def", "ghi"]가 있고  
문자열 "ef"를 포함한 문자열은 제외하고 꼬리 문자열을 만들면 "abcghi"가 됩니다.  
문자열 리스트 str_list와 제외하려는 문자열 ex가 주어질 때, str_list에서 ex를 포함한 문자열을 제외하고 만든 꼬리 문자열을 return하도록 solution 함수를 완성해주세요.

#### 입출력 예
|str_list |	ex | result|
|---------|-----|-------|
|["abc", "def", "ghi"] |	"ef" |	"abcghi"|
|["abc", "bbc", "cbc"] |	"c"	| ""|

<br>

#### :pencil2:첫 번째 코드
```python

def solution(str_list, ex):
answer = ''

    for i in str_list:
        if ex not in i:
            answer += i
        
    return answer
```

<br>

#### :pencil2:두 번째 코드
```python
def solution(str_list, ex):
    answer = ''
    a = []
    
    for i in str_list:
        if ex not in i:
            a.append(i)
    answer = "".join(a)
        
    return answer
```

<br>

#### :sparkles:느낀점 
- 같은 코드를 실행 하였는데 처음에는 실행 실패를 하였고, 
다른 코드로 작성해 실행 후 통과 되었지만 다시 실행했을 때 실패했습니다.   
다시 처음 코드로 실행하니 성공하였는데 실행할 때마다 결과가 달라지는 이유를 모르겠습니다.

#### :sparkles:새롭게 알게된 것
- "".join(리스트)를 이용하면 매개변수로 들어온 ["abc", "ghi"] 이런 식의 리스트를 'abcghi'의 문자열로 합쳐서 반환해주는 함수입니다.
  - "_".join(a) => abc_ghi
  - ".".join(a) => abc.ghi
  
