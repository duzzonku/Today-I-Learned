# Data Structure 1

과목: python
작성일: 2026년 1월 26일

# Data Structure

## 데이터 구조

- 여러 데이터를 효과적으로 사용 관리하기 위한 구조

## 메서드 (method)

- 객체에 속한 함수
- 객체 : 특정 데이터와 그 데이터를 처리하는 기능을 하나로 묶은 것
- 문자열, 리스트, 딕셔너리 등 각 데이터 구조 고유의 메서드 보유
- 데이터를 효율적으로 조작하거나 특정 기능을 수행하기 위해 제공
- 클래스 내부에 정의되는 함수

---

## 매서드 호출 방법

### ‘hello’.capitalize()

- 데이터 타입 객체 . 매서드()

```python
# 문자열 메서드
print('hello'.capitalize())  # Hello
```

```python
# 리스트 메서드
numbers = [1, 2, 3]
numbers.append(4)
print(numbers)  # [1, 2, 3, 4]
```

---

# 공통 시퀀스 매서드

### .index(x)

- 시퀀스에서 첫 번째로 일치하는 항목  x의 인덱스를 반환
- 없으면 ValueError 발생

```python
# index
text = 'banana'
print(text.index('a))  # 1

my_list = [1, 2, 3]
print(my_list.index(2))  # 1
```

### .count(x)

- 시퀀스에서 등장하는 항목 x의 개수 반환

```python
# count
text = 'banana'
print(text.count('a'))  # 3

my_list = [1, 2, 2, 3, 3, 3]
print(my_list.index(3))  # 3
```

---

# 불변 시퀀스 매서드 ( 문자열 전용 )

## 탐색 및 검증

### .find(x)

- x의 첫 번째 위치를 반환
- 없으면 -1을 반환
- x의 위치를 알아야 할 경우 사

```python
# find
text = 'banana'
print(text.find('a'))  # 1
print(text.find('z'))  # -1
```

---

### .isupper()

- 문자열 내 모든 케이스 문자가 대문자이지 확인
- T/F 반환

```python
# isupper
string1 = 'HELLO'
string2 = 'Hello'
print(string1.isupper())  # True
print(string2.isupper())  # False
```

---

### .islower()

- 문자열 내의 모든 케이스 문자가 소문자로 이루어져 있는지 확인
- T/F 반환

```python
# islower
print(string1.islower())  # False
print(string2.islower())  # False
```

---

### .isalpha()

- 문자열의 모든 문자가 알파벳이고
- 하나 이상의 문자가 포함되어 있으면 True 반환

```python
# isalpha
string1 = 'Hello'
string2 = '123heis98576ssh'
print(string1.isalpha())  # True
print(string2.isalpha())  # False
```

---

## 문자열 조작 - 새로운 문자열 반환(문자열은 불변)

### .replace(old, new[ , count])

- 기존 문자열에서 ‘old’라는 부분 문자열이 ‘new’로 모두 바뀐 문자열 반환
- [ ] : 선택 인자 (문서적 표기법)

```python
# replace
text = 'Hello, world! world world'
new_text1 = text.replace('world', 'Python')
new_text2 = text.replace('world', 'Python', 1)
print(new_text1)  # Hello, Python! Python Python
print(new_text2)  # Hello, Python! world world
```

---

### .strip([chars)

- 선행과 후행 문자가 제거된 문자열의 복사본을 돌려줌
- chars : 제거할 문자 집합을 지정하는 문자열
- 생략되거나 None이라면, chars 인자의 기본값은 공백을 제거

```python
# strip
# 사용자 입력 등에서 불필요한 공백이 포함된 경우
text = '   Hello    World   '

# 1. 아무것도 지정하지 않으면 '공백(띄어쓰기, 탭, 엔터)'을 제거
clean_text = text.strip()

print(clean_text)
# 결과: 'Hello    World'
# (주의: 문자열 중간의 공백은 제거되지 않음)

# 2. 제거할 문자를 지정하는 경우
text = '!!!Hello World!!!'
print(text.strip('!'))
# 결과: 'Hello World'

# [심화] 문자열 집합으로 제거 (순서 상관 없음)
# 'w', '.', 'c', 'o', 'm' 중 하나라도 양쪽 끝에 있으면 계속 제거
url = 'www.example.com'
print(url.strip('w.com'))
# 결과: 'example'
# (왼쪽의 'www.'과 오른쪽의 '.com'이 모두 제거됨)
```

---

### .split(sep = None, maxsplit = -1)

- sep을 구분자 문자열로 사용하여 문자열에 있는 단어들의 리스트 반환
- maxsplit이 주어지면 최대 maxsplit 번의 분할이 수행
- sep이 지정되지 않거나 None이면, 연속된 공백 문자는 단일한 구분자로 간주
- 문자열이 선행이나 후행 공백을 포함해도 결과는 시작과 끝에 빈 문자열 포함 X

```python
# split
# 1. 공백을 기준으로 분리 (기본 동작)
# - 여러 개의 공백도 하나로 처리하며, 앞뒤 공백은 무시함
text = '  Hello    Python  '
print(None)
# 결과: ['Hello', 'Python’]

# 2. 특정 문자를 기준으로 분리
# - 지정한 문자를 기준으로 '엄격하게' 분리함 (빈 문자열 발생 가능)
data = '10,20,,30'
print(None)
# 결과: ['10', '20', '', '30']

# 3. 분할 횟수 제한 (maxsplit)
# - 앞에서부터 1번만 자르고 나머지는 그대로 둠
path = 'User/admin/documents'
print(path.split('/', maxsplit=1))
# 결과: ['User', 'admin/documents']
```

---

### .join(iterable)

- iterable의 문자열을 연결한 문자열을 반환

```python
# join
words = ['Python', 'is', 'awesome']

sentence1 = None
sentence2 = None

print(sentence1)  # Python is awesome
print(sentence2)  # Python-is-awesome
```

---

## 기타 문자열 조작 매서드

```python
# capitalize
text = 'heLLo, woRld!'
new_text1 = text.capitalize()
print(new_text1)  # Hello, world!

# title
new_text2 = text.title()
print(new_text2)  # Hello, World!

# upper
new_text3 = text.upper()
print(new_text3)  # HELLO, WORLD!

# lower
new_text4 = text.lower()
print(new_text4)  # hello, world!

# swapcase
new_text5 = text.swapcase()
print(new_text5)  # HEllO, WOrLD!
```

---

# 가변 시퀀스 매서드 (리스트 전용)

## 값 추가 및 삭제

### .append(x)

- 리스트 마지막에 항목 x를 추가
- 반환 값 X

```python
# append
my_list = [1, 2, 3]
my_list.append(4)
print(my_list)  # [1, 2, 3, 4]
# append는 None을 반환합니다.
print(my_list.append(4))  # None
```

---

### .extend(iterable)

- iterable의 모든 항목들을 리스트 끝에 추가 (+= 같은 기능)
- 반복 가능한 객체가 아니면 추가 불가

```python
# extend
my_list = [1, 2, 3]
my_list.extend([4, 5, 6])
print(my_list)  # [1, 2, 3, 4, 5, 6]
```

```python
# extend와 append의 비교
my_list.append([5, 6, 7])
print(my_list)  # [1, 2, 3, 4, 5, 6, [5, 6, 7]]
```

```python
# my_list.extend(100)  # TypeError: 'int' object is not iterable
```

---

### .insert(i, x)

- x를 지정한 인덱스 i 위치에 삽입

```python
# insert
my_list = [1, 2, 3]
my_list.insert(1, 5)
print(my_list)  # [1, 5, 2, 3]
```

---

### .remove(x)

- 리스트에서 첫 번째로 일치하는 항목을 삭제

```python
# remove
my_list = [1, 2, 3, 2, 2, 2]
my_list.remove(2)
print(my_list)  # [1, 3, 2, 2, 2]
```

---

### .pip() 또는 .pop(i)

- 리스트에서 지정한 인덱스의 항목을 제거하고 반환
- 작성하지 않을 경우 마지막 항목을 제거

```python
# pop
my_list = [1, 2, 3, 4, 5]
item1 = my_list.pop()
item2 = my_list.pop(0)

print(item1)  # 5
print(item2)  # 1
print(my_list)  # [2, 3, 4]
```

---

### .clear()

- 리스트의 모든 항목을 제거

```python
# clear
my_list = [1, 2, 3]
my_list.clear()
print(my_list)  # []
```

---

## 정렬

### .reverse()

- 리스트의 순서를 역순으로 변경 (정렬 X)
- 반환 값 X

```python
# reverse
my_list = [1, 3, 2, 8, 1, 9]
my_list.reverse()
# reverse는 None을 반환합니다.
# print(my_list.reverse())  # None
# reverse는 원본 리스트를 변경합니다.
print(my_list)  # [9, 1, 8, 2, 3, 1]
```

---

### . sort()

- 원본 리스트를 오름차순으로 정렬
- 반환 값 X

```python
# sort
my_list = [3, 2, 100, 1]
my_list.sort()
# sort는 None을 반환합니다.
# print(my_list.sort())  # None
# sort는 원본 리스트를 변경합니다.
print(my_list)  # [1, 2, 3, 100]

# sort(내림차순 정렬)
my_list.sort(reverse=True)
print(my_list)  # [100, 3, 2, 1]
```

---

# 복사

## 객체와 참조

### Mutable(가변) 객체

- 생성 후 내용을 변경할 수 있는 객체
- ex) 리스트(list), 딕셔너리(dict), 집합(set)

```python
# 가변(mutable) 객체
print('가변(mutable) 객체 예시')
a = [1, 2, 3, 4]
b = a
b[0] = 100

print(f'a의 값: {a}')  # [100, 2, 3, 4]
print(f'b의 값: {b}')  # [100, 2, 3, 4]
print(f'a와 b가 같은 객체를 참조하는가? {a is b}')  # True
```

---

### Immutable(불변) 객체

- 생성 후 내용을 변경할 수 없는 객체
- ex) 정수, 실수, 문자열, 튜플

```python
# 불변(immutable) 객체
print('\n불변(immutable) 객체 예시')
a = 20
b = a
b = 10

print(f'a의 값: {a}')  # 20
print(f'b의 값: {b}')  # 10
print(a is b)  # False
```

---

### 변수 할당

- 객체에 대한 참조를 생성하는 과정
- 변수는 객체의 메모리 주소를 가리키는 Label
- ‘=’ 연산자를 사용하여 변수에 값을 할당
- 할당 시 새로운 객체 생성 or 기존 객체에 대한 참조 생성

---

### id() 함수를 사용한 메모리 주소 확인

- id() 함수를 사용하여 객체의 메모리 주소 확인 가능
- is 연산자를 통해 두 변수가 같은 객체를 참조하는지 확인 가능

```python
# id() 함수를 사용한 메모리 주소 확인
print('\n메모리 주소 확인')
x = [1, 2, 3]
y = x
z = [1, 2, 3]

print(f'x의 id: {id(x)}')
print(f'y의 id: {id(y)}')
print(f'z의 id: {id(z)}')
print(f'x와 y는 같은 객체인가? {x is y}')
print(f'x와 z는 같은 객체인가? {x is z}')
```

---

### 가변 / 불변 메모리 관리 방식의 이유

- 성능 최적화
    - 불변 객체 : 변경이 불가능하므로, 여러 변수가 동일한 객체를 안전하게 공유
    - 가변 객체 : 내용 수정이 빈번할 때, 기존 객체 직접 수정 가능

- 메모리 효율성
    - 불변 객체: 같은 값을 가진 여러 변수가 같은 객체 참조 → 메모리 사용 최소화
    - 가변 객체 : 크기가 큰 데이터를 효율적으로 수정 가능

---

## 얕은 복사

- 객체의 최상위 요소만 새로운 메모리에 복사하는 방법
- 내부에 중첩된 객체가 있다면, 그 객체의 참조만 복사

---

## 얕은 복사 구현 방법

### 1차원 리스트에서의 얕은 복사

### 1. 리스트 슬라이싱

- 원본 리스트와 동일한 내용의 새로운 리스트 생성
- 해당 요소들이 참조하는 주소가 리스트에 복사

```python
# 1차원 리스트에서의 얕은 복사 (리스트 슬라이싱)
a = [1, 2, 3]
b = a[:]

print(a)  # [1, 2, 3]
print(b)  # [1, 2, 3]
```

---

### 2. copy() 메소드

- list.copy() : 원본 리스트와 동일한 내용을 가진 새로운 리스트 객체 반환

```python
# 1차원 리스트에서의 얕은 복사 (copy 메서드)
a = [1, 2, 3]
b = a.copy()

print(a)  # [1, 2, 3]
print(b)  # [1, 2, 3]
```

---

### 3. list() 함수

```python
# 1차원 리스트에서의 얕은 복사 (list() 함수)
a = [1, 2, 3]
d = list(a)
a[0] = 100
print(a)  # [100, 2, 3]
print(d)  # [1, 2, 3]
```

---

## 얕은 복사의 한계

```python
# 얕은 복사의 한계
print('\n다차원 리스트 얕은 복사의 한계')
a = [1, 2, [3, 4, 5]]
b = a[:]

b[0] = 999
print(a)  # [1, 2, [3, 4, 5]]
print(b)  # [999, 2, [3, 4, 5]]

b[2][1] = 100
print(a)  # [1, 2, [3, 100, 5]]
print(b)  # [999, 2, [3, 100, 5]]

print(f'a[2]와 b[2]가 같은 객체인가? {a[2] is b[2]}')  # True
```

---

### 1차원 리스트와 다차원 리스트에서의 차이점

- 1차원 리스트
    - 얕은 복사로 충분히 독립적인 복사본 만들 수 있음
- 다차원 리스트
    - 최상위 리스트만 복사되고, 내부 리스트는 여전히 원본과 같은 객체 참조

---

# 깊은 복사

- 객체의 모든 수준의 요소를 새로운 메모리에 복사하는 방법
- 중첩된 객체까지 모두 새로운 객체로 생성

---

### deepcopy() 함수

- copy 모듈에서 제공하는 deepcopy() 함수 사용

```python
# 깊은 복사
import copy

a = [1, 2, [3, 4, 5]]
b = copy.deepcopy(a)

b[2][1] = 100

print(a)  # [1, 2, [3, 4, 5]]
print(b)  # [1, 2, [3, 100, 5]]
print(f'a[2]와 b[2]가 같은 객체인가? {a[2] is b[2]}')  # False
```

- 중첩된 객체에서의 깊은 복사

```python
# 복잡한 중첩 객체
print('복잡한 중첩 객체 깊은 복사')
original = {
    'a': [1, 2, 3],
    'b': {'c': 4, 'd': [5, 6]},
}
copied = copy.deepcopy(original)

copied['a'][1] = 100
copied['b']['d'][0] = 500

print(f'원본: {original}')  # {'a': [1, 2, 3], 'b': {'c': 4, 'd': [5, 6]}}
print(f'복사본: {copied}')  # {'a': [1, 100, 3], 'b': {'c': 4, 'd': [500, 6]}}
print(
    f"original['b']와 copied['b']가 같은 객체인가? {original['b'] is copied['b']}"
)  # False

```

---

# List Comprehension

- 간결하고 효율적인 리스트 생성 방법

---

## List Comprehension 구조

### [표현식 for 변수 in 순회 가능한 객체 if 조건]

- 유용한 문법이지만 남용 X

```python
# 사용 전
numbers = [1, 2, 3, 4, 5]
squared_numbers = []

for num in numbers:
    squared_numbers.append(num**2)

print(squared_numbers)

```

```python
# 사용 후
squared_numbers2 = [num**2 for num in numbers]
# squared_numbers2 = list(num**2 for num in numbers)
print(squared_numbers2)
```

- 2차원 배열 생성 시 사용 (인접 행렬 생성)

```python
# "2차원 배열 생성 시 (인접행렬 생성 시)"
data1 = [[0] * (5) for _ in range(5)]
print(data1)

# 또는
data2 = [[0 for _ in range(5)] for _ in range(5)]
print(data2)

"""
[[0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0],
 [0, 0, 0, 0, 0]]
"""
```

---

# 리스트를 생성하는 3가지 방법

### 1. list comprehension

- 우수한 성능

```python
# 2. list comprehension
result2 = [i for i in range(10)]
# result2 = list(i for i in range(10))

print(result2)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### 2. map

- 특정 상황 (int, str 등 내장 함수와 함께 사용할 때) 가장 빠름

```python
# 3. map
result3 = list(map(lambda i: i, range(10)))

print(result3)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### 3. for loop

- 일반적으로 가장 느리다고 알려져 있음
- 여러 줄에 걸친 복잡한 조건문이나 예외 처리 등이 필요할 때, 유일한 선택지

```python
result1 = []
for i in range(10):
    result1.append(i)
    
 print(result1)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

---

# 매서드 체이닝

- 여러 매서드를 연속해서 호출하는 방식

---

## 문자열에서의 메서드 체이닝

1. text.swapcase() : 대소문자 반전
2. .replace (’l’, ‘z’) : 소문자 ‘ㅣ’을 ‘z’로 교체

```python
# 문자열 메서드 체이닝
text = 'heLLo, woRld!'
new_text = text.swapcase().replace('l', 'z')
print(new_text)  # HEzzO, WOrLD!
```

```python
# 1. 단계별로 실행하기
text = 'heLLo, woRld!'
step1 = text.swapcase()
print('1단계 결과:', step1)  # HEllO, WOrLD!

step2 = step1.replace('l', 'z')
print('2단계 결과:', step2)  # HEzzO, WOrLD!

# 2. 한 줄로 실행하기 (위와 동일한 결과)
new_text = text.swapcase().replace('l', 'z')
print('최종 결과:', new_text)  # HEzzO, WOrLD!
```

---

## 리스트에서의 메서드 체이닝

- 리스트 메서드 체이닝의 흔한 실수

```python
# 1. 리스트 메서드 체이닝의 흔한 실수
numbers = [3, 1, 4, 1, 5, 9, 2]

# [실수 1] sort()는 None을 반환하므로, 변수에 아무것도 저장되지 않음
result = numbers.copy().sort()
print(result)  # None (정렬된 리스트를 기대했으나 None 출력)

# [실수 2] append()가 반환한 None 뒤에 메서드를 이을 수 없음
numbers.append(7).extend(
    [8, 9]
)  # AttributeError: 'NoneType' object has no attribute 'extend'
```

- 올바른 해결책

```python
# 2. 올바른 해결책 (Good Cases)
numbers = [3, 1, 4, 1, 5, 9, 2]

# [해결 1] 내장 함수 sorted() 사용 (추천)
# sorted()는 정렬된 '새로운 리스트'를 반환하므로 변수에 할당 가능
# (원본을 건드리지 않으므로 copy()를 굳이 쓸 필요 없음)
sorted_numbers = sorted(numbers)
print(sorted_numbers)  # [1, 1, 2, 3, 4, 5, 9]

# [해결 2] 메서드를 단계별로 나누어 작성
# 체이닝을 포기하고, 명확하게 한 줄씩 실행
copied_list = numbers.copy()
copied_list.sort()
print(copied_list)  # [1, 1, 2, 3, 4, 5, 9]
```

---

## 매서드 체이닝 주의사항

- 모든 메서드가 체이닝을 지원 X
    - 메서드가 객체를 반환할 때만 체이닝 가능

- None을 반환하는 메서드는 메서드 체이닝 불가능
    - ex) 리스트의 append(), sort()