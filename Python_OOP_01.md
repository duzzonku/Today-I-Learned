# OOP 1

과목: python
작성일: 2026년 1월 28일

# 절차 지향 프로그래밍

- 함수와 로직 중심 작성
- 데이터를 순차적으로 처리
- 처음부터 끝까지 실행되는 결과물이 중요

```python
# 절차 지향 사고
# 예: 변수와 함수를 별개로 다룸
name = 'Alice'
age = 25

def introduce(name, age):
    print(f'안녕하세요, {name}입니다. 나이는 {age}살입니다.')

introduce(name, age)
```

---

# 객체 지향 프로그래밍

- 클래스는 설계도
- 인스턴스는 실제 물건
- 사람(객체) 안에 name, age와 이와 관련된 기능 포함

```python
# 객체 지향 사고
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f'안녕하세요, {self.name}입니다. 나이는 {self.age}살입니다.')

alice = Person('Alice', 25)
alice.introduce()  # 객체가 자신의 정보를 출력
```

---

## 절차 지향

- 데이터와 해당 데이터를 처리하는 함수가 분리
- 함수 호출의 흐름이 중요
- 어떤 순서로 처리할까?

---

## 객체 지향

- 데이터와 해당 데이터를 처리하는 메서드를 하나의 객체로 묶음
- 객체 간 상호작용과 메시지 전달이 중요
- 어떤 객체가 이 문제를 해결할까?
- 이 객체는 어떤 속성과 기능을 가질까?
- 스스로 기능을 수행하는 능동적 존제

---

# 객체

- 실제 존재하는 사물을 추상화 한 것
- ‘속성’과 ‘동작’을 가짐
- 속성
- 메서드
- 고유

---

# 클래스

- 객체를 만들기 위한 설계도
- 관련된 데이터(속성)와 기능(메서드)을 하나의 ‘묶음’으로 정의하는 설계도
- 파이썬에서 타입을 표현하는 방법
- 여러 개의 객체를 쉽게 만들 수 있음

---

## 클래스 정의

- class 키워드
- 클래스 이름 : 파스칼 케이스 방식으로 작성
- 파스칼 케이스 : 단어의 앞 부분만 대문자로 표현

---

## 클래스 예시

- __ init __ 메서드 : ‘생성자 메서드’
- __ : 매직 메서드 → 호출 시점을 파이썬이 결정
- 새로운 객체를 만들 때 필요한 초기값 설정

```python
class Person:
    def __init__(self, name, age):
        self.name = name  # 인스턴스 속성
        self.age = age  # 인스턴스 속성

    def introduce(self):
        print(f'안녕하세요. 저는 {self.name}, 나이는 {self.age}살입니다.')
```

---

# 인스턴스

- 클래스를 통해 생성된 객체

---

## 클래스와 인스턴스

- 클래스를 정의한다는 것은 ‘공통된 특성과 기능을 가진 틀’을 만드는 것
- 실제 활동하는 개별 객체들은 이 틀에서 생성된 인스턴스
- 공통된 특성과 기능을 가진 틀을 만드는 것은 새로운 타입을 만드는 행위
- 문자열 타입의 변수는 str 클래스로 생성된 인스턴스
    
    ### 하나의 객체는 특정 클래스의 인스턴스다.
    

```python
class Singer:
    pass

# iu와 bts는 Singer 클래스의 인스턴스
name = 'Alice'
print(type(name))

data = [1,2,3]
print(type(data))

iu = Singer()
bts = Singer()

# 문자열 변수 name은 (정확히는 'Alice')는 str 클래스의 인스턴스
print(type(iu)) # <class '__main__.Singer'>
print(type(bts))

# 문자열 name이 사용할 수 있는 메서드인 split()은 z클래스 str에 정의되어 있음
# data가 사용할 수 있는 메서드인 append()는 클래스 list에 정의되어 있음
```

---

### [1,2,3]. sort()

- 리스트 : 정렬
- 객체 : 행동
- 인스턴스 : 메서드

---

## 클래스 구조

### 생성자 메서드

- 인스턴스 생성 시 자동 호출되는 메서드
- __ init __이라는 이름의 메서드로 정의
- 인스턴스 변수의 초기화 담당

---

### 인스턴스 변수 ( 속성 )

- 각 인스턴스별 고유한 속성
- self 변수명 형태로 정의
- 인스턴스마다 독립적인 값 유지

---

### 클래스 변수 ( 속성 )

- 모든 인스턴스가 공유하는 속성
- 클래스 내부에서 직접 정의

```python
class Circle:
    # 생성자 메서드
    def __init__(self, radius):
        self.radius = radius

    pi = 3.14

# 인스턴스 생성
c1 = Circle(1)
c2 = Circle(2)

# 인스턴스 변수(속성) 접근
print(c1.radius) # 1
print(c2.radius) # 2

# 클래스 변수(공통 속성) 접근
print(c1.pi) # 3.14
print(c2.pi) # 3.14
```

---

# 매서드

- 클래스 내부에 정의된 함수
- 해당 객체가 어떻게 동작할지를 정의

---

## 인스턴스 메서드

- 인스턴스의 상태를 조작하거나 동작을 수행
- 클래스 내부에 정의되는 메서드의 기본
- 반드시 첫 번째 인자로 인스턴스 자신(self)을 받음
- 인스턴스의 속성에 접근하거나 변경 가능
- 인스턴스마다 독립적으로 행동할 수 있게 만드는 것
- 생성자 메서드 : 인스턴스 메서드

```python
class Counter:
    def __init__(self):
        self.count = 0

    # 인스턴스 메서드
    def increment(self):
        # 이 메서드를 호출하는 인스턴스의 변수 count를 1 증가시키는 메서드
        self.count += 1

c1 = Counter()
c2 = Counter()
# 인스턴스 메서드 호출
print(c1.count) # 0

c1.increment()
print(c1.count) # 1
print(c2.count) # 0
```

---

### self 동작 원리 → 인스턴스 메서드의 첫 번째 인자가 반드시 인스턴스 자신인 이유

- upper 메서드를 사용해 문자열 ‘hello’ 대문자로 변경
- 하지만 실제 파이썬 내부 동작
- 객체 지향 방식의 메서드로 호출하는 표현 ( 단축형 호출)
- hello 라는 문자열 객체가 스스로 메서드르르 호출하여 코드를 동작하는 객체 지향적인 표현

---

### 생성자 메서드

- 인스턴스 객체가 생성될 때 자동으로 호출되는 메서드
- 인스턴스 변수들의 초기값 설정

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greeting(self):
        print(f'안녕하세요 {self.name}입니다.')

person1 = Person('지민')  # 인스턴스가 생성되었습니다.
person1.greeting()  # 안녕하세요. 지민입니다.
# Person.greeting(person1)
print(person1.name) # 지민

```

---

### 클래스 메서드

- 클래스 변수를 조작
- 클래스 레벨의 동작 수행
- @classmethod 데코레이터를 사용하여 정의
- 호출 시, 첫 번째 인자로 해당 메서드를 호출하는 클래스가 전달됨
- 클래스를 인자로 받아 클래스 속성을 변경하거나 읽는 데 사용

```python
class Person:
    population = 0

    def __init__(self, name):
        self.name = name
        # 클래스 메서드를 통해 인스턴스가 생성될 때마다 인구 수 증가
        Person.increase_population()

    @classmethod
    def increase_population(cls):
        cls.population += 1
    

# 인스턴스 생성
person1 = Person('Alice')
person2 = Person('Bob')

# 클래스 변수 접근
print(Person.population) # 2
```

---

### 스태틱 메서드 (정적 메서드)

- 클래스, 인스턴스와 상관없이 독립적으로 작동하는 메서드
- @staticmethod 데코레이터를 사용하여 정의
- 호출 시 자동으로 전달받는 인자 X
- 인스턴스나 클래스 속성에 직접 접근하지 않는 ‘도우미 함수’ 비슷한 역

```python
class MathUtils:
    # 정적 메서드
    # 클래스나 인스턴스에 의존하지 않고 독립적으로 동작
    # 정적 메서드는 클래스나 인스턴스의 상태를 변경하지 않음
    @staticmethod
    def add(a, b):
        return a + b

# 정적 메서드 호출
print(MathUtils.add(3, 5)) # 8

```

---

무엇을 바꾸는가? 가 메서드 선택의 기준

### 클래스가 사용해야 할 것

- 클래스 메서드 → 모두 다 호출 가능
- 스태틱 메서드

### 인스턴스가 사용해야 할 것

- 인스턴스 메서드 → 모두 다 호출 가능

- 호출 가능하다고 써도 되는 것은 아님
