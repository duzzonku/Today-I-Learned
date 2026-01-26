# Basic_Syntax_02

과목: python
작성일: 2026년 1월 26일

# 리스트

- 여러 개의 값을 순서대로 저장하는, 변경 가능한(mutable) 시퀀스 자료형

---

## 리스트 표현

- 대괄호 [ ] 안에 값들을 쉼표( , )로 구분하여 만듦
- 숫자, 문자열, 심지어 다른 리스트까지 모든 종류의 데이터를 담을 수 있음
- 값을 추가, 수정, 삭제하는 등 자유롭게 변경 가능

```python
# 리스트 표현
my_list_1 = []
my_list_2 = [1, 'a', 3, 'b', 5]
my_list_3 = [1, 2, 3, 'Python', ['hello', 'world', '!!!']]
```

---

## 리스트의 시퀀스 특징

- 리스트 : 시퀀스
- 문자열처럼 인덱싱, 슬라이싱, 길이 확인, 반복 등 공통 기능 모두 사용 가능

```python
my_list = [1, 'a', 3, 'b', 5]

# 인덱싱
print(my_list[1])  # a

# 슬라이싱
print(my_list[2:4])  # [3, 'b']
print(my_list[:3])  # [1, 'a', 3]
print(my_list[3:])  # ['b', 5]
print(my_list[::2])  # [1, 3, 5]
print(my_list[::-1])  # [5, 'b', 3, 'a', 1]

# 길이
print(len(my_list))  # 5
```

---

# 중첩 리스트

- 다른 리스트를 값으로 가진 리스트

---

## 중첩 리스트 접근

- 인덱스를 연달아 사용하여 안쪽 리스트의 값에 접근 가능

1. 바깥 리스트의 인덱스로 안쪽 리스트 선택
2. 선택된 안쪽 리스트에 다시 한번 인덱스 사용

```python
# 중첩된 리스트 접근
my_list = [1, 2, 3, 'Python', ['hello', 'world', '!!!']]

print(len(my_list))  # 5
print(my_list[4][-1])  # !!!
print(my_list[-1][1][0])  # w
```

---

# 리스트의 가변성

- 한번 생성된 리스트는 ‘그 내용을 자유롭게 수정, 추가, 삭제’ 가능
- 문자열의 불변성과 정반대

## 1. 인덱싱으로 값 수정하기

```python
# 1. 인덱싱으로 값 수정
my_list = [1, 2, 3, 4, 5]
my_list[1] = 'two'
print(my_list)  # [1, 'two', 3, 4, 5]
```

## 2. 슬라이싱으로 여러 값 한번에 바꾸기

```python
# 2. 슬라이싱으로 값 수정
my_list = [1, 2, 3, 4, 5]
my_list[2:4] = ['three', 'four']
print(my_list)  # [1, 2, 'three', 'four', 5]
```

---

# 튜플 (tuple)

- 여러 개의 값을 순서대로 저장하는 변경 불가능한 시퀀스 자료형
- 소괄호 ( ) 안에 값들을 쉼표( , )로 구분하여 만듦
- 모든 종류의 데이터 담을 수 있음
- 한번 만들어지면 절대 수정 X
- 소괄호 없이도 생성 가능
- 단일 요소 튜플을 만들 때는 반드시 후행 쉼표 사용

```python
# 튜플 표현
my_tuple_1 = ()
my_tuple_2 = (1,)
my_tuple_3 = (1, 'a', 3, 'b', 5)
my_tuple_4 = 1, 'hello', 3.14, True
```

---

# 시퀀스로서의 튜플

- 튜플 역시 시퀀스
- 인덱싱, 슬라이싱, 길이 확인, 반복 등 공통 기능 모두 사용 가능

```python
my_tuple = (1, 'a', 3, 'b', 5)

# 인덱싱
print(my_tuple[1])  # a

# 슬라이싱
print(my_tuple[2:4])  # (3, 'b')
print(my_tuple[:3])  # (1, 'a', 3)
print(my_tuple[3:])  # ('b', 5)
print(my_tuple[::2])  # (1, 3, 5)
print(my_tuple[::-1])  # (5, 'b', 3, 'a', 1)

# 길이
print(len(my_tuple))  # 5
```

---

# 튜플의 불변성

## 튜플 변경 시도하기

- 한번 생성된 튜플은 그 내용을 절대 수정, 추가, 삭제 X

```python
# 튜플은 불변

my_tuple = (1, 'a', 3, 'b', 5)

# TypeError: 'tuple' object does not support item assignment
my_tuple[1] = 'z'
```

---

## 튜플이 불변 자료형인 이유

- 내부 동작과 안전한 데이터 전달에 사용 → 데이터의 안정성, 무결성 보장
- ex) 다중 할당, 값 교환, 함수 다중 반환 값 등

```python
# 다중 할당
x, y = 10, 20
print(x)  # 10
print(y)  # 20

# 실제 내부 동작
(x, y) = (10, 20)
```

```python
# 값 교환
x, y = 1, 2
x, y = y, x

# 실제 내부 동작
temp = (y, x)  # 튜플 생성
x, y = temp  # 튜플 언패킹
print(x, y)  # 2 1
```

---

# range

- 연속된 정수 시퀀스를 생성하는, 변경 불가능한 자료형
- 주로 반복문과 함께 사용
- 실제 모든 숫자를 메모리에 저장 X
- 시작 값, 끝 값, 간격이라는 ‘규칙’만 기억

```python
# 주로 반복문과 함께 활용 예정
for i in range(1, 10):
    print(i)  # 1 2 3 4 5 6 7 8 9

for i in range(1, 10, 2):
    print(i)  # 1 3 5 7 9
```

---

## range 기본 구문

### range(start, stop, step)

- range()는 1개, 2개 또는 3개의 매개변수(인자)를 가질 수 있음
- 매개변수 : 함수를 정의할 때, 함수가 받을 값을 나타내는 변수
- 인자 : 함수를 호출할 때, 실제로 전달되는 값

---

## range 매개변수 별 특징

### range(stop)

- 매개변수가 하나면 stop으로 인식
- start는 0이, step은 1이 기본값으로 자동 설정

### range(start, stop)

- 매개변수가 2개면 start, stop으로 인식
- step은 1이 기본값으로 자동 설정

### range(start, stop, step)

- 모든 매개변수를 직접 지정

```python
# range 표현
my_range_1 = range(5)
my_range_2 = range(1, 10)
my_range_3 = range(5, 0, -1)

print(my_range_1)  # range(0, 5)
print(my_range_2)  # range(1, 10)
print(my_range_3)  # range(5, 0, -1)

# 리스트로 형 변환 시 데이터 확인 가능
print(list(my_range_1))  # [0, 1, 2, 3, 4]
print(list(my_range_2))  # [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(my_range_3))  # [5, 4, 3, 2, 1]
```

---

# range의 규칙

## 1. 값의 범위 규칙

- stop 값은 생성되는 시퀀스에 포함 X

## 2. 증가 / 감소 값 (step) 규칙

- step : 숫자 시퀀스의 간격과 방향 결정

### 1. step이 양수일 때 ( 기본값 : 1)

- 숫자가 start부터 stop을 향해 증가
- range(1, 10, 2) → 1,3,5,7,9

```python
# step이 양수일 때 (기본값 1)
# 시작 값이 끝 값보다 작은 경우 (정상)
print(list(range(1, 5)))  # [1, 2, 3, 4]
# 시작 값이 끝 값보다 큰 경우
print(list(range(5, 1)))  # []
```

### 2. step이 음수일 때

- 숫자가 start부터 stop을 향해 감소
- start 값 > stop 값

```python
# step이 음수일 때
# 시작 값이 끝 값보다 큰 경우 (정상)
print(list(range(5, 1, -1)))  # [5, 4, 3, 2]
# 시작 값이 끝 값보다 작은 경우
print(list(range(1, 5, -1)))  # []
```

---

# dict (딕셔너리)

- key - value 쌍으로 이루어진 순서와 중복이 없는 변경 가능한 자료형

---

## 딕셔너리 표현

- 중괄호 { } 안에 값들이 쉼표로 구분되어 있음
- 값 1개는 키와 값이 쌍으로 구성
- key : 값을 식별하기 위한 고유한 ‘이름표’ → 중복 불가
- Value : 키에 해당하는 실제 데이터
- 각 값에는 순서 X

```python
my_dict_1 = {}
my_dict_2 = {'key': 'value'}
my_dict_3 = {'apple': 12, 'list': [1, 2, 3]}

print(my_dict_1)  # {}
print(my_dict_2)  # {'key': 'value'}
print(my_dict_3)  # {'apple': 12, 'list': [1, 2, 3]}
```

---

## 딕셔너리 규칙

- 고유해야 함 → key 중복 X
- 변경 불가능한 자료형만 사용 가능
    - ex) str, int, float, tuple
- 어떤 자료형이든 자유롭게 사용 가능

---

# 딕셔너리 값 접근

- key를 사용하여 해당 Value를 꺼내 옴
- key에 접근 시 대괄호 [ ] 사용

```python
# 딕셔너리는 키에 접근해 값을 얻어냄
my_dict = {'name': '홍길동', 'age': 25}

print(my_dict['name'])  # '홍길동'
print(my_dict['test'])  # KeyError: 'test'
```

```python
# 딕셔너리 값 추가 및 변경
my_dict = {'apple': 12, 'list': [1, 2, 3]}

# 추가
my_dict['banana'] = 50
print(my_dict)  # {'apple': 12, 'list': [1, 2, 3], 'banana': 50}

# 변경
my_dict['apple'] = 100
print(my_dict)  # {'apple': 100, 'list': [1, 2, 3], 'banana': 50}
```

### 딕셔너리는 언제 사용?

- 데이터에 순서 필요 X
- 각 데이터에 의미 있는 이름을 붙여 관리하고 싶을 때 사용

---

# set (세트)

- 순서와 중복이 없는 변경 가능한 자료
- 중괄호 { } 안에 값들을 쉼표로 구분하여 만듦
- 수학에서의 집합과 동일한 연산 처리
- 중복 허용 X
    - 똑같은 값은 단 하나만
- 순서가 없음
    - 인덱싱 (set[0]) 이나 슬라이싱(set[0:2]) 사용 X

```python
my_set_1 = set()
my_set_2 = {1, 2, 3}
my_set_3 = {1, 1, 1}

print(my_set_1)  # set()
print(my_set_2)  # {1, 2, 3}
print(my_set_3)  # {1}
```

---

# 세트의 집합 연산

- 수학의 ‘집합’과 동일

```python
# 세트의 집합 연산산
my_set_1 = {1, 2, 3}
my_set_2 = {3, 6, 9}

# 합집합
print(my_set_1 | my_set_2)  # {1, 2, 3, 6, 9}

# 차집합
print(my_set_1 - my_set_2)  # {1, 2}

# 교집합
print(my_set_1 & my_set_2)  # {3}
```

---

# Other Types

## None

- ‘값이 없음’을 표현하는 특별한 데이터 타입
- 내용물이 없는 ‘빈 상자’
- 숫자 0, 빈 문자열 (’ ‘)과는 다름

```python
# my_variable에는 아직 아무 값도 할당하고 싶지 않을 
my_variable = None
print(my_variable)  # None
```

---

## Boolean

- 참(True)과 거짓 (False), 단 2가지 값만 가지는 데이터 타입
- 비교 / 논리 연산의 평가 결과로 사용
- 주로 조건 / 반복문과 함께 사용

```python
is_active = True
is_logged_in = False

print(is_active)  # True
print(is_logged_in)  # False
print(10 > 5)  # True
print(10 == 5)  # False
```

---

# Collection

- 여러 개의 값을 하나로 묶어 관리하는 자료형을 통칭하는 말
- str, list, tuple, range, set, dict 데이터 타입 모두 Collection에 분류

| **컬렉션명** | **변경 가능 여부** | **순서 존재 여부** |
| --- | --- | --- |
| **str** | **X** | **O** |
| **list** | **O** | **O** |
| **tuple** | **X** | **O** |
| **dict** | **O** | **X** |
| **set** | **O** | **X** |
- 시퀀스 : str, list, tuple
- 비시퀀스 : set, dict

---

# 불변과 가변

## 불변

- 변경 불가
- 안전성
- 예측 가능
- ex) str, tuple, range

```python
# immutable (불변)
my_str = 'hello'
my_str[0] = 'z'  # TypeError: 'str' object does not support item assignment
```

## 가변

- 변경 가능
- 유연성
- 효율성
- ex) list, dict, set

```python
# mutable (가변)
my_list = [1, 2, 3]
my_list[0] = 100
print(my_list)  # [100, 2, 3]
```

---

# 형변환

- 한 데이터 타입을 다른 데이터 타입으로 변환하는 과정

---

## 암시적 형변환

- 파이썬이 연산 중에 자동으로 데이터 타입을 변환하는 것
- 정수와 실수의 연산에서 정수가 실수로 변환
- Boolean과 Numeric Type에서만 가능

```python
# 정수(int)와 실수(float)의 덧셈
print(3 + 5.0)  # 8.0

# 불리언(bool)과 정수(int)의 덧셈
print(True + 3)  # 4

# 불리언간의 덧셈
print(True + False)  # 1
```

---

## 명시적 형변환

- 개발자가 변환하고 싶은 타입을 직접 함수로 지정하여 변환하는 것
- ex) int(), float(), str(), list(), tuple(), set()

### str → int

- 형식에 맞는 숫자만 가능

```python
print(int('1'))  # 1
# ValueError: invalid literal for int() with base 10: '3.5'
# print(int('3.5'))
print(int(3.5))  # 3
print(float('3.5'))  # 3.5
```

### int → str

- 모두 가능

```python
print(str(1) + '등')  # 1등
```

---

# 연산자

## 복합 연산자

- 연산과 할당이 함께 이뤄짐
- ex) +=, -=, %=, **= 등

```python
# 복합 연산자
y = 10
y -= 4
# y = y - 4
print(y)  # 6

z = 7
z *= 2
print(z)  # 14

w = 15
w /= 4
print(w)  # 3.75

q = 20
q //= 3
print(q)  # 6
```

---

## 비교 연산자

- 두 값을 비교하여 그 관계가 맞는지 틀리는지를 True 또는 False로 반환
- ex) <, ≤, ≠, is, is not 등 ..

### == 연산자

- 값(데이터)이 같은지를 비교
- 동등성

```python
# == 연산자
print(2 == 2.0)  # True
print(2 != 2)  # False
print('HI' == 'hi')  # False
print(1 == True)  # True
```

---

### is 연산자

- 객체 자체가 같은지를 비교
- 식별성
- 두 변수가 완전히 동일한 객체를 가리키는지
- 즉, 메모리 주소가 같은지를 확인할 때 사용

```python
# is 비교 연산자
# SyntaxWarning: "is" with a literal. Did you mean "=="?

print(1 is True)  # False
print(2 is 2.0)  # False
```

---

### is 대신 ==를 사용해야 하는 이유

- is는 정체성을, is는 가치를 비교하기 때문
- is
    - 두 변수가 완전히 동일한 메모리 주소의 객체를 가리키는지
    - 정체성이 같은지 확인
- ==
    - 두 변수가 가리키는 객체의 내용
    - 값이 같은지를 확인

---

## is를 값 비교에 사용하면 안되는 이유

### ‘의도와 다른 결과를 낳기 때문’

```python
# 왜 is 대신 ==를 사용해야 하나?

# 1(정수)과 True(불리언)는 다른 객체이다.
print(1 is True)  # False

# 1과 True의 '값'은 논리적으로 같다.
print(1 == True)  # True

# 2(정수)와 2.0(실수)은 다른 객체이다.
print(2 is 2.0)  # False

# 2와 2.0의 '값'은 논리적으로 같다.
print(2 == 2.0)  # True
```

---

### is 연산자는 언제 사용

- 주로 싱글턴 객체를 비교할 때 사용

---

### 싱글턴 객체란?

- 특정 값에 대해 파이썬 전체에서 단 하나의 객체만 생성되어 재사용되는 특별한 객체
- 여러 변수가 이 값을 가지더라도, 모두 미리 만들어진 하나의 객체를 함께 가리키므로 항상 같은 메모리 주소를 가짐
- ex) None, True, False

---

### 싱글턴 객체를 비교할 때

- is 연산자는 두 변수가 완전히 동일한 객체를 가리키는지
- 메모리 주소가 같은지를 확인할 떄 사용
- 단 하나의 객체만 생성되어 재사용되는 싱글턴 객체 비교에 적합

```python
# 싱글턴 객체 비교할 때
x = None
# 권장
if x is None:
    print('x는 None입니다.')
# 비권장
if x == None:
    print('x는 None입니다.')
```

```python

x = True
y = True

print(x is y)  # True
print(True is True)  # True
print(False is False)  # True
print(None is None)  # True
```

---

### 리스트나 객체 비교 시 주의사항

- 리스트, 다른 가변 객체를 비교할 때, 값 자체가 같은지 확인하려면 == 사용
- 두 변수가 완전히 동일한 객체를 가리키는지 확인해야 한다면 is 사용

```python
a = [1,2,3]
b = [1,2,3]

print(a == b) # True (두 리스트의 값은 동일)
print(a is b) # False ( 서로 다른 리스트 객체)

# b가 a를 그대로 참조하도록 할 경우
b = a
print(a is b)
```

---

### == 와 is 정리

- 값 비교에는 == 사용
- 객체 비교에는 is 사용
- is는 주로 싱글턴 객체에 대한 비교시 용

---

## 논리 연산자

- 여러 개의 조건을 조합하거나
- True / False 값을 반대로 뒤집을 때 사용 (and, or, not이 대표적)

```python
# 논리 연산자
print(True and False)  # False
print(True or False)  # True
print(not True)  # False
print(not 0)  # True
```

---

### and

- 논리곱
- 두 피연산자 모두 True인 경우에만 전체 표현식을 True로 평가

---

### or

- 논리합
- 두 피연산자 중 하나라도 True인 경우, 전체 표현식을 True 평가

---

### not

- 논리부정
- 단일 피연산자를 부정

---

### 비교 연산자와 함께 사용 가능

```python
# 논리 연산자 & 비교 연산자
num = 15
result = (num > 10) and (num % 2 == 0)
print(result)  # False

name = 'Alice'
age = 25
result = (name == 'Alice') or (age == 30)
print(result)  # True
```

---

# 단축 평가

- 논리 연산에서 두 번째 피연산자를 평가하지 않고 결과를 결정하는 동작
- 코드 실행 최적화
- 불필요한 연산 피할 수 있음
- 코드 흐름 제어
- 오류 방

---

### ‘True’와 ‘False’에 대한 새로운 시각

- 거짓으로 취급되는 값들
    - False, 0, 빈 문자열 “”, 빈 리스트 [ ], None 등  ‘비어있거나 없다’는 느낌
- 참으로 취급되는 값들
    - True, 그리고 ‘거짓’이 아닌 모든 값
    - 1, -10, ‘hello’, [1, 2] 등 내용이 있는 값

---

## 단축 평가 동작 정리

### and 연산자

- 하나라도 ‘거짓’이면 바로 ‘거짓’
- and는 연산을 왼쪽에서 오른쪽으로 진행하다, 처음 만나는 ‘거짓’값 바로 반환
- 만약 끝까지 갔는데 모든 값이 ‘참’이면, 맨 마지막 ‘참’ 값 반환

```python
# 1
# 준비물 1: 내용이 있는 문자열
item1 = '지도'
# 준비물 2: 내용이 있는 문자열
item2 = '나침반'

# '지도' -> '나침반'
result = item1 and item2
print(f'최종적으로 챙긴 물건: {result}')
# >> 최종적으로 챙긴 물건: 나침반
```

```python
# 2
item1 = '지도'
# 준비물 2: 내용이 없는 빈 문자열
item2 = ''

# '지도' -> ''
result = item1 and item2
print(f'최종적으로 챙긴 물건: "{result}"')
# >> 최종적으로 챙긴 물건: ''
```

```python
# 3
# 준비물 1: 내용이 없는 빈 문자열
item1 = ''
item2 = '나침반'
# ''
result = item1 and item2
print(f'최종적으로 챙긴 물건: "{result}"')
# >> 최종적으로 챙긴 물건: ''
```

### or 연산자

- 하나라도 ‘참’이면 바로 ‘참’
- or는 연산을 왼쪽에서 오른쪽으로 진행하다, 처음 만나는 ‘참’값 바로 반환
- 만약 끝까지 갔는데 모든 값이 ‘거짓’이면, 맨 마지막 ‘거짓’ 값을 반환

---

## 멤버쉽 연산자

- 특정 값이 시퀀스나 다른 컬렉션 안에 포함되어 있는지 확인하는 연산자

### in

- 왼쪽 피연산자가 오른쪽 피연산자의 시퀀스에 속하는지 확인

### not in

- 왼쪽 피연산자가 오른쪽 피연산자의 시퀀스에 속하지 않는지를 확인

```python
# 멤버십 연산자

word = 'hello'
numbers = [1, 2, 3, 4, 5]

print('h' in word)  # True
print('z' in word)  # False

print(4 not in numbers)  # False
print(6 not in numbers)  # True
```

---

## 시퀀스형 연산자

- 시퀀스 자료형 (str, list, tuple)에 특별한 의미로 사용되는 연산자
- + : 결합 연산자 → 시퀀스를 연결하는 기능
- *  : 반복 연산자 → 시퀀스를 반복하는 기능

```python
# 시퀀스형 연산자

print('Gildong' + ' Hong')  # Gildong Hong
print('hi' * 5)  # hihihihihi

print([1, 2] + ['a', 'b'])  # [1, 2, 'a', 'b']
print([1, 2] * 2)  # [1, 2, 1, 2]
```

---

# 연산자 우선순위

1. ( )
2. [  ] (인덱싱, 슬라이싱)
3. **
4. +, - (양수 / 음수)
5. *, /, //, %
6. +, - ( 산술 연산자)
7. 비교 연산자
8. is, is not (객체 비교)
9. is, not in (멤버십 연산자)
10. not (논리 부정)
11. and (논리 AND)
12. or (논리 or)
