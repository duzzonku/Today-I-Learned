# 파이썬_module

# 모듈

- 한 파일로 묶인 변수와 함수의 모음
- 특정 기능을 하는 코드가 작성된 파이썬 파일(.py)
- ex) math 내장 모듈 → 파이썬이 미리 작성해둔 수학 관련 변수와 함수가 작성된 모듈

---

### Import 문 사용

- 같은 이름의 함수가 여러 모듈에 있을 때 충돌 방지
- .(dot) 연산자 → 점 왼쪽 객체에서 점 오른쪽 이름을 찾아라
- 코드가 길어질 수 있음

```python
import math

print(math.pi)  # 3.141592653589793
print(math.sqrt(4))  # 2.0
```

---

### from 절 활용

- 코드가 짧고 간결
- 정의된 모듈의 위치를 알기 어려움
- 사용자가 선언한 변수, 함수와 겹치게 되어 모듈에서 정의한 값이나 동작 이루어지지 않을 가능성 존재

```python
# from 절 사용
from math import pi, sqrt

print(pi)  # 변수명
print(sqrt(4))  # 함수명

```

```python
# from 절 단점
from math import sqrt

math_result = sqrt(16)  # 실수형 4.0

def sqrt(x):  # 사용자가 정의한 sqrt 함수
    return str(x**0.5)

my_result = sqrt(16)  # 문자열 4.0
```

---

### from 절 주의사항

- 서로 다른 모듈에서 import된 변수나 함수 이름이 같은 경우 이름 충돌 발생
- 나중에 import된 것만 유효

```python
## 같은 이름인 경우 덮어쓰기 주의
from math import sqrt  # math.sqrt가 먼저 import됨
from my_math import sqrt  # my_math.sqrt가 math.sqrt를 덮어씀

result = sqrt(9)  # math.sqrt가 아닌 my_math.sqrt가 사용됨
```

- 모든 요소를 한번에 import 하는 * 표기 권장 X

```python
## 모든 요소를 한 번에 import 하는 * 은 권장하지 않음
from math import *
from my_math import sqrt, tangent  # 어느 함수가 math 모듈과 중복되는지 모름

# 아래는 사용자가 임의로 정의한 변수들
a = 100
c = 200
e = 300  # math 모듈의 자연상수 e를 사용할 수 없게 됨
```

---

### ‘as’ 키워드

- as 키워드 사용하여 별칭 부여 → 이름 충돌 해결

```python
from math import sqrt
from my_math import sqrt as my_sqrt

print(sqrt(4))  # 2.0
print(my_sqrt(4))  # 2.0
```

- import 되는 함수나 변수명이 너무 길거나 자주 사용할 경우 사용

```python
## (참고) pandas와 matplotlib 패키지 설치해야 정상 동작
import pandas as pd
import matplotlib.pyplot as plt

# 별칭을 부여하지 않으면 길고 불편함
df = pandas.DataFrame()
matplotlib.pyplot.plot(x, y)
```

---

## 파이썬 표준 라이브러리

- 파이썬 언어와 함께 제공되는 다양한 모듈과 패키지의 모음
- 파이썬을 설치하면 자동으로 사용 가능
- 복잡한 작업도 쉽게 처리 가능
- 별도 설치 필요 X → 바로 import 해서 사용 가능
- ex) math, random, sys, json, email

---

## 패키지

- 연관된 모듈들을 하나의 디렉토리에 모아 놓은 것 = 코드 꾸러미

---

### 파이썬 외부 패키지

- 필요한 기능을 사용하기 위해 직접 설치해서 쓰는 패키지
- ex) 엑셀 파일 조작(pandas, openpyxl), 데이터 시각화(matploblib), 웹 데이터 수집(requests)
- pip를 통해 설치

---

### pip

- 외부 패키지들을 설치하도록 도와주는 파이썬의 패키지 관리 시스템
- 최신 버전 / 특정 버전 / 최소 버전 명시하여 설치 가능

---

### requests 패키지

- 파이썬에서 웹에 요청을 보내고 응답을 받는 걸 아주 쉽게 만들어주는 외부 패키지
- .get(url) : 주어진 url로 요청하는 requests 패키지 메소드
- .json : 문자열로 이루어진 json 자료형을 dict 자료형으로 변환시키는 메소드

```python
# requests 패키지
$ pip install requests

import requests

# 공휴일 정보 API
url = "https://date.nager.at/api/v3/publicholidays/2026/KR"

# URL 주소에 요청을 보내서 응답 데이터를 받아 딕셔너리로 변경
response = requests.get(url).json()
print(response)
```

---

### 패키지 사용 목적

- 모듈의 이름 공간을 구분하여 충돌 방지
- 모듈을 효율적으로 관리할 수 있도록 돕는 역할

---

# 제어문

- 코드의 실행 흐름을 제어하는 데 사용되는 구문
- 조건에 따라 코드 블록을 실행하거나 반복적으로 코드를 실행
- 상황에 따라 다른 코드 실행 or 같은 코드를 여러번 반복 가능

---

## 조건문

- 주어진 조건식을 평가하여 해당 조건이 참(True)인 경우에만 코드를 실행하거나 건너뜀
- if / elif / else

```python
score = 87

if score > 95:
    print('축하합니다')
else:
    print('수고하셨습니다.')
    
# else 없어도 상황에 따라서 elif까지만 사용해도 무관

# if만 써도 가능
```

---

### if 문

- 조건문의 기본 형태

---

### elif 문

- 이전의 조건을 만족하지 못하고 추가로 다른 조건이 필요할 때 사용
- 여려 개의 elif 문 사용 가능

---

### else 문

- 모든 조건들을 만족하지 않으면 실행됨

---

## 복수 조건문

- 조건식을 동시에 검사하는 것이 아니라 ‘순차적’으로 비교
- 조건식의 순서에 따라 원하는 결과가 나오지 않을 수 있음

```python
# 복수 조건문
## 순서 1. 결과: 매우 나쁨
dust = 155

if dust > 150:
    print('매우 나쁨')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')

## 순서 2. # 결과: 보통
dust = 155

if dust > 30:
    print('보통')
elif dust > 80:
    print('나쁨')
elif dust > 150:
    print('매우 나쁨')
else:
    print('좋음')
```

---

## 중첩 조건문

- 조건문 내부에 또 다른 조건문 작성 가능

```python
# 출력: 매우 나쁨
#      위험해요! 나가지 마세요!
dust = 480

if dust > 150:
    print('매우 나쁨')
    if dust > 300:
        print('위험해요! 나가지 마세요!')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')
```

---

## 반복문

- 주어진 코드 블록을 여러 번 반복해서 실행하는 구문

---

### for문

- 반복 가능한 객체의 요소들을 반복하는 데 사용
- 주로 반복 가능한 객체 요소의 개수만큼 반복
- 반복 횟수가 정해져 있음
- 반복 가능한 객체 : 요소를 하나씩 반환할 수 있는 모든 객체  ex list, tuple, str, dict, set
- for 변수 in 반복 가능한 객체:
    
           코드 블록
    

```python
# for문
student_list = ['Alice', 'Bob', 'Charlie']

#for 다음에 작성하는 임시변수는 단수형으로 사용하는 것을 권장
for student in student_list:
    print(f'Hello, {student}!')
    
# for문 작동 원리
item_list = ['apple', 'banana', 'coconut']

for item in item_list:  # item: 반복 변수
    print(item)
```

### 문자열 순회

- 문자열 반복시 문자가 반복 변수에 할당되어 반복 수행

```python
# 문자열 순회
country = 'Korea'

for char in country:
    print(char)
```

---

### range 순회

- 특정 숫자 범위만큼 반복을 하고 싶을 때 range 함수 사용

```python
# range 순회
for i in range(5):
    print(i)
```

---

### 딕셔너리 순회

- dict 자료형은 비시컨스 자료형

```python
# for문 dictionary 순회
my_dict = {
    'x': 10,
    'y': 20,
    'z': 30,
}

for key in my_dict:
    print(key)
    print(my_dict[key])
```

---

### 인덱스로 리스트 순회

- 리스트의 요소가 아닌 인덱스로 접근하여 해당 요소들을 변경
- 인덱스를 사용하면 리스트의 원하는 위치에 있는 값을 읽거나 변경 가능

```python
# 인덱스 순회
numbers = [4, 6, 10, -8, 5]

for i in range(len(numbers)):
    numbers[i] = numbers[i] * 2

print(numbers)
```

---

### 중첩된 반복문

```python
# 중첩 반복문
outers = ['A', 'B']
inners = ['c', 'd']

for outer in outers:
    for inner in inners:
        print(outer, inner) # (A, c) (A,d) (B, c) (B, d)
```

---

### 중첩 리스트 순회

- 안쪽 리스트 요소에 접근하려면 바깥 리스트를 순회하면서 중첩 반복을 사용해 각 안쪽 반복 순회

```python
# 중첩 리스트 순회
elements = [['A', 'B'], ['c', 'd']]

# 1
for elem in elements:
    print(elem) # ['A', 'B'] ['c', 'd']

# 2
for elem in elements:
    for item in elem:
        print(item) # A B c d

```

---

### while문

- while 조건이 참인 동안 반복 == 조건이 거짓이 될 때까지 반복
- 반복 횟수가 정해지지 않은 경우 주로 사용
- 반드시 종료 조건이 필요

```python
# while문 기본 1
a=0

while a < 3:
    print(a)
    a += 1

print('끝')

# while문 기본 2
input_value = ''
while input_value != 'exit':  # exit 를 입력하면 반복 종료
    input_value = input("Enter a value: ")
    print(input_value)

```

---

### 사용자 입력에 따른 반복

- while문을 사용한 특정 입력 값에 대한 종료 조건 활용하기

```python
# while문 사용자 입력에 따른 반복
number = int(input('양의 정수를 입력해주세요.: '))

while number <= 0:
    if number < 0:
        print('음수를 입력했습니다.')
    else:
        print('0은 양의 정수가 아닙니다.')

    number = int(input('양의 정수를 입력해주세요.: '))

print('잘했습니다!')
```

---

## 반복 제어

- for문과 while문은 매 반복마다 본문 내 모든 코드를 실행
- BUT 일부만 실행하는 것이 필요할 때가 존재
- 반드시 반복문 내에서 사

---

### break

- 해당 키워드를 만나게 되면 남은 코드를 무시하고 반복 즉시 종료
- 반복을 끝내야 할 명확한 조건이 있을 때 사용

```python
# break 키워드 기본
for i in range(10):
    if i == 5:
        break
    print(i)  # 0 1 2 3 4
```

```python
# break 키워드 (for문)
# 리스트에서 첫번째 짝수만 찾은 후 반복 종료하기
numbers = [1, 3, 5, 6, 7, 9, 10, 11]
found_even = False

for num in numbers:
    if num % 2 == 0:
        print('첫 번째 짝수를 찾았습니다:', num) # 6
        found_even = True
        break

if not found_even:
    print('짝수를 찾지 못했습니다')
```

```python
# break 키워드 (while문)
# 프로그램 종료 조건 만들기
number = int(input('양의 정수를 입력해주세요.: '))

while number <= 0:
    if number == -9999:
        print('프로그램을 종료합니다.')
        break

    if number < 0:
        print('음수를 입력했습니다.')
    else:
        print('0은 양의 정수가 아닙니다.')

    number = int(input('양의 정수를 입력해주세요.: '))
print('잘했습니다!')

```

---

### continue

- 해당 키워드를 만나게 되면 다음 코드는 무시하고 다음 반복을 수행

```python
# continue 키워드 기본
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)  # 1 3 5 7 9
```

```python
# 리스트에서 홀수만 출력하기
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in numbers:
    if num % 2 == 0:
        continue
    print(num)
```

---

## 빈 코드 블록 키워드

### pass

- ‘아무 동작도 하지 않음’을 명시적으로 나타내는 키워드
- 코드의 틀을 유지하거나 나중에 내용을 채우기 위한 용도로 사용
- 반복문 뿐만 아니라 함수, 조건문에서도 사용 가능

```python
# pass 키워드 (while 문)
while True:
    if condition1:
        break
    elif condition2:
        pass  # 빈 코드를 의미
    else:
        print('출력')
```

```python
# pass 키워드 (if 문)
if condition:
    pass  # 아무런 동작도 수행하지 않음
else:
    pass  # 구조를 잡을 뿐
```

```python
# pass 키워드 (함수 정의)
def my_function():
    pass  # pass 없으면 오류 발생
```

---

## map 함수

- 반복 가능한 데이터 구조의 모든 요소에 function을 적용하고, 그 결과 값들을 map object로 묶어서 반환
- map(function, iterable)

```
numbers = [1, 2, 3]
result = map(str, numbers)

print(result)  # <map object at 0x00000239C915D760>
print(list(result))  # ['1', '2', '3']
```

```python
# map 함수- input과 함께 사용
# 터미널 창에서 1 2 3 입력 (공백 주의)
numbers1 = input().split()
print(numbers1)  # ['1', '2', '3']

## 터미널 창에서 1 2 3 입력 (공백 주의)
numbers2 = list(map(int, input().split()))
print(numbers2)  # [1, 2, 3]
```

```python
# map 함수 - lambda와 함께 사용
numbers = [1, 2, 3, 4, 5]

def square(x):
    return x**2

# lambda 미사용
squared1 = list(map(square, numbers))
print(squared1)  # [1, 4, 9, 16, 25]

# lambda 사용
squared2 = list(map(lambda x: x**2, numbers))
print(squared2)  # [1, 4, 9, 16, 25]
```

---

## zip 함수

- 여러 개의 반복 가능한 데이터 구조를 묶어 같은 위치에 있는 값을 하나의 튜플로 만들어 zip object 반환
- 전체 값을 확인하려면 list나 tuple로 형 변환 필수

```python
girls = ['jane', 'ashley']
boys = ['peter', 'jay']
pair = zip(girls, boys)

print(pair)  # <zip object at 0x000001C76DE58700>
print(list(pair))  # [('jane', 'peter'), ('ashley', 'jay')]
```

```python
# 여러 개의 리스트를 동시에 조회할 때

kr_scores = [10, 20, 30, 50]
math_scores = [20, 40, 50, 70]
en_scores = [40, 20, 30, 50]

for student_scores in zip(kr_scores, math_scores, en_scores):
    print(student_scores) # (10,20,40) (20,40,20) (30,50,30) (50,70,50)

```
