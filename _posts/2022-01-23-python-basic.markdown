---
layout: post
title: python 문법 1 (주석, 자료형(숫자형, 문자열))
date: 2022-01-23 22:00:00 +0900
category: python
---
# 주석
```python
# 한줄 주석
"""여러줄 주석"""
```

---

# 숫자형
- 정수형 int
- 실수 float
- 지수 float
- 8진수
- 16진수
- 사칙연산 가능
```python
a =  3
b =  4
# + - *
print(a**b) # 제곱
print(a/b) # 나누기
print(a//b) # 몫이 나온다
print(a%b) # 나머지가 나온다
```

---

# 문자열

### 문자열 - 4가지

```python
"Hello World"
'python is fun'
"""Life is too short,
You need python 줄바꿈 가능"""
'''Life is too short,
You need
python 줄바꿈 가능'''

'백슬러시 가능 \'  \" '

a = "python"
b = " is fun"
print(a + b) # 더하기
print(a *  10) #곱하기 python 10번 출력
```
---
### 문자열 - 인덱싱
```python
a = "Life is too short, You need Python"
print(a[2]) # i
print(a[-1]) # 마지막 문자 n
print(a[-2]) # o
```
---
### 문자열 - 슬라이싱 [이상:미만:간격]
```python
a = "20010331Rainy"
print(a[0:4])
print(a[:5]) # 비우면 처음부터 시작
print(a[8:]) # 8부터 끝까지

a = "12345678"
print(a[::2]) # 1357
```
---
### 문자열 - 포맷팅
```python
# %s string %c char %d integer 
# %f float %o 8진수 %x 16진수 %% Literal % {문자 '%' 자체}

number =  10
day = "three"

a = "I ate %d apples. so i was sick for %s days."  % (number, day)
# I ate 10 apples. so i was sick for three days.
```
---
### 3.6 version 이상부터 가능
```python
name =  "mazino"
b =  f"나의 이름은 {name} 입니다"
print(b)
```
---
### % 간격 . 소수점 남기는 자리수 f
```python
a = "%0.4f"  %  3.23423423  # 3.2342
print(a)
```
---
#### .count : 변수안에 포함된 문자열 갯수 
#### .find : 처음에 나오는 문자열 인덱스
#### 없으면 -1 return
```python
a =  "hobby"
print(a.count("b"))
print(a.find("b"))
print(a.find("x")) # -1
```
### .join : 기준으로 쪼개준다
```python
a = ",".join("abcd") # a,b,c,d,
```
#### .upper(), .lower(), .strip() < 양쪽 공백 지우기
#### .replace, .split() 띄어쓰기 기준으로 list return