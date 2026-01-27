# Data Structure 2

과목: python
작성일: 2026년 1월 27일

# 비시퀀스 데이터 구조

## 딕셔너리 (Dictionary)

- 키와 값을 짝지어 저장하는 구조
- 해시 테이블을 사용하여 키-값 쌍 관리
- 키를 통한 값의 삽입, 삭제, 검색이 데이터의 크기와 관계없이 매우 빠름
- 키 (key) : hashable한 고유 값
- 값 (Value) : 중복 가능 + 어떤 자료형도 저장 가능

---

## 딕셔너리 메서드

### .get(key[, default])

- 키 연결된 값을 반환
- 키가 없으면 None 혹은 기본 값 반환

```python
# get
person = {'name': 'Alice', 'age': 25}

print(person.get('name')) # Alice
print(person.get('country')) # None
print(person.get('country', 'Unknown')) # Unknown
print(person['country'])  # KeyError: 'country'
```

---

### .keys()

- 딕셔너리 키를 모은 객체를 반환

```python
# keys
person = {'name': 'Alice', 'age': 25}

print(person.keys())  # dict_keys(['name', 'age'])
for item in person.keys(): # name age
    print(item)
```

---

### .values()

- 딕셔너리 값을 모은 객체 반환

```python
# values
person = {'name': 'Alice', 'age': 25}

print(person.values())  # dict_values(['Alice', 25])
for item in person.values(): # Alice 25
    print(item)
```

---

### .items()

- 딕셔너리 키 / 값 쌍을 모은 객체 반환

```python
# items
person = {'name': 'Alice', 'age': 25}

print(person.items())  # dict_items([('name', 'Alice'), ('age', 25)])
for key, value in person.items():
    print(key, value)
```

---

### .pop( key[, default] )

- 키를 제거하고 연결됐던 값을 반환
- 없으면 에러나 default를 반환

```python
# pop
person = {'name': 'Alice', 'age': 25}

print(person.pop('age'))  # 25
print(person)  # {'name': 'Alice'}
print(person.pop('country', None))  # None
print(person.pop('country'))  # KeyError: 'country'
```

---

### .clear( )

- 딕셔너리의 모든 키 / 값 쌍을 제거

```python
# clear
person = {'name': 'Alice', 'age': 25}

person.clear()
print(person)
```

---

### .setdefault( key[, default] )

- 키와 연결된 값 반환
- 키가 없다면 default와 연결한 키를 딕셔너리에 추가하고 default 반환

```python
# setdefault
person = {'name': 'Alice', 'age': 25}

print()  # KOREA
print(person)  # {'name': 'Alice', 'age': 25, 'country': 'KOREA'}
```

---

### .update( [other] )

- other 가 제공하는 키 / 값 쌍으로 딕셔너리를 갱신하고 기존 키는 덮어씀
- 마지막 값만 출

```python
# update
person = {'name': 'Alice', 'age': 25}
other_person = {'name': 'Jane', 'country': 'KOREA'}

person.update(other_person)
print(person)  # {'name': 'Jane', 'age': 25, 'country': 'KOREA'}

person.update(age=100, address='SEOUL')
print(
    person
)  # {'name': 'Jane', 'age': 100, 'country': 'KOREA', 'address': 'SEOUL'}
```

---

# 세트

- 고유한 항목들의 정렬되지 않은 컬렉션
- 해시 테이블을 사용하여 데이터 저장
- 항목의 고유성 효율적으로 보장
- 항목의 추가, 삭제, 존재 여부 확인 (in 연산)이 데이터 크기 관계없이 매우 빠름
- 수학적인 집합 연산 간편하게 수행 가능

---

### .add(x)

- 세트에 x를 추가

```python
# add
my_set = {'a', 'b', 'c', 1, 2, 3}

my_set.add(4)
print(my_set)

my_set.add(4) # 중복 불가
print(my_set)
 
```

---

### . update (iterable)

- 세트에 다른 iterable 요소를 추가

```python
# update
my_set = {'a', 'b', 'c', 1, 2, 3}

my_set.update([1, 4, 5])
print(my_set)  # {'c', 2, 3, 1, 'b', 4, 5, 'a'}
```

---

### . clear( )

- 세트의 모든 항목을 제거

```python
# clear
my_set = {'a', 'b', 'c', 1, 2, 3}

my_set.clear()
print(my_set)  # set()
```

---

### . remove(x)

- 세트에서 항목 x를 제거
- 항목 x가 없을 경우 keyError

```python
# remove
my_set = {'a', 'b', 'c', 1, 2, 3}

my_set.remove(2)
print(my_set)

my_set.remove(10)  # KeyError: 10
```

---

### .pop( )

- 세트에서 임의의 요소를 제거하고 반환
- 무작위 X

```python
# pop
my_set = {'a', 'b', 'c', 1, 2, 3}

element = my_set.pop()

print(element) 
print(my_set) 
```

---

### . discard(x)

- 세트 s에서 항목 x를 제거
- remove와 달리 에러 X → 출력 X

```python
# discard
my_set = {'a', 'b', 'c', 1, 2, 3}

my_set.discard(2)

print(my_set)
my_set.discard(10)
```

---

## 세트의 집합 메서드

### 1. set1 .difference(set2)

- set1 - set2
- set1에는 들어있지만 set2에는 없는 항목으로 세트를 생성 후 반환

### 2. set1 .intersection(set2)

- set1 & set2
- set1, set2 모두 들어있는 항목으로 세트를 생성 후 반환

### 3. set1 .issubset(set2)

- set1 ≤ set2
- set1의 항목이 모두 set2에 들어있으면 True 반환

### 4. set1 .issuperset(set2)

- set ≥ set2
- set1이 set2의 항목을 모두 포함하면 True 반환

### 5. set1 .union(set2)

- set1 | set2
- set1 또는 set2에 (혹은 둘 다) 들어있는 항목으로 세트를 생성 후 반환

```python
# 집합 메서드
set1 = {0, 1, 2, 3, 4}
set2 = {1, 3, 5, 7, 9}
set3 = {0, 1}

print(set1.difference(set2))  # {0, 2, 4}
print(set1.intersection(set2))  # {1, 3}
print(set1.issubset(set2))  # False
print(set3.issubset(set1))  # True
print(set1.issuperset(set2))  # False
print(set1.union(set2))  # {0, 1, 2, 3, 4, 5, 7, 9}
```

---

# 딕셔너리의 확장 : defaultdict

- 딕셔너리에 존재하지 않는 키를 조회할 때, 자동으로 ‘기본값’을 생성해주는 자료구조
- keyError 걱정 없이 값을 수정하거나 추가할 때 유용

---

## 기본 딕셔너리 vs defaultdict 비교

- 상황 : 주어진 문자열에서 각 문자의 등장 횟수 세기

```python
# 기존: 기본 딕셔너리
text = 'banana'
counts = {}

for char in text:
    if char not in counts:  # 키가 있는지 매번 확인해야 함
        counts[char] = 0
    counts[char] += 1

print(counts)  # {'b': 3, 'a': 3, 'n': 2}
```

```python
# 개선: defaultdict 활용
from collections import defaultdict

text = 'banana'
counts = defaultdict(int)  # 기본값을 정수(0)로 설정

for char in text:
    # 키 확인 불필요! 없으면 0으로 자동 생성 후 +1
    counts[char] += 1

print(counts)  # defaultdict(<class 'int'>, {'b': 1, 'a': 3, 'n': 2})
```

---

## defaultdict 구문 및 활용 가이드

### defaultdict(자료형)

- 숫자 세기 : defaultdict(int)
    - 키가 없으면 0으로 초기화
- 그룹핑 / 리스트 모으기 : defaultdict(list)
    - 키가 없으면 빈 리스트 [ ]로 초기화
- defaultdict는 조회만 해도 키가 생성
    - print(my_dict[’missing_key’])를 하면 0이 출력되면서 키가 추가
- 단순히 키가 있는지 확인할 때는 주의해서 사용

- 색깔별 과일 분류하기

```python
# 색상별 과일 분류
fruits = [('red', 'apple'), ('yellow', 'banana'), ('red', 'cherry')]
fruit_by_color = defaultdict(list)

for color, fruit in fruits:
    # color 키가 없으면 빈 리스트 생성 -> append 바로 가능
    pass

print(
    fruit_by_color
)  # defaultdict(<class 'list'>, {'red': ['apple', 'cherry'], 'yellow': ['banana']})
print(
    dict(fruit_by_color)
)  # {'red': ['apple', 'cherry'], 'yellow': ['banana']}
```

---

# 해시 테이블 (hash table)

- ‘키(key)’와 ‘값(Value)’을 짝지어 저장하는 자료구조

---

## 해시 테이블 원리

1. 키를 해시 함수를 통해 해시 값으로 변환 → 검색 X
2. 변환된 해시 값을 인덱스로 삼아 데이터를 저장하거나 찾음
3. 이로 인해 검색, 삽입, 삭제를 매우 빠르게 수행

---

## 해시 (Hash)

- 임의의 크기를 가진 데이터를 고정된 크기의 고유한 값으로 변환하는 것
- 생성된 해시 값(고유한 정수)은 해당 데이터를 식별하는 ‘지문’ 역할
- 이 해시 값을 이용해 해시 테이블에 데이터 저장
- 변환을 수행하는 것이 해시 함수

---

## 해시 함수 (Hash Function)

- 임의 길이 데이터를 입력 받아 고정 길이(정수)로 변환해주는 함수
- 이 정수가 바로 해시 값
- 주로 해시 테이블을 구현할 때, 매우 빠른 검색 및 데이터 저자 위치 결정을 위해 활용
- ‘해시 알고리즘’

---

## set 요소 & dict의 키와 해시 테이블 관계

### set

- 각 요소를 해시 함수로 변환해 나온 해시 값에 맞춰 해시 테이블 내부 버킷에 위치시킴
- ‘순서’라기보다 ‘버킷 위치(인덱스)’가 요소 위치 결정
- 따라서 set는 순서 보장 X

### dict

- 키(key) → 해시 함수 → 해시 값 → 해시 테이블에 저장
- 단 set와 달리 ‘삽입 순서’는 유지한다
    - 즉, 키를 추가한 수서대로 반복문 순회할 때 나오게 됨
    - 사용자에게 보여지는 키 순서는 삽입 순서가 유지되도록 설계된

---

## set의 pop 매서드 - 정수

- 정수(숫자) 값은 해시 값이 숫자 자기 자신과 동일 or 단순 계산으로 고정
- 버킷에 배치된 순서대로 pop
- 같은 정수는 항상 같은 해시 값
- set의 pop()은 ‘임의의 요소’를 제거하고 반환함
- ‘무작위’가 아닌 ‘임의’라는 의미에서 **“무작위”**
- 내부적으로 해시 테이블(버킷)을 참조하기 때문에, 실행 때마다 다른 요소가 먼저 나올 수 있음

```python
# 정수
my_set = {3, 2, 1, 9, 100, 4, 87, 39, 10, 52}

print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set.pop())
print(my_set)
```

---

## set의 pop 매서드 - 문자열

- 문자열 해시 시, 파이썬 인터프리터 시작 때 설정되는 난수 시드가 달라질 수 있음
    
    → 동일한 데이터라도 매번 해시 값이 달라짐 → 버킷 배치 달라짐
    
- 해시 계산 시 파이썬의 해시 난수화 적용
- 실행마다 순서 변경될 수 있음 → ‘a’의 해시 값도 매번 바뀔 수 있음

```python
# 문자열
my_str_set = {'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j'}

print(my_str_set.pop())
print(my_str_set.pop())
print(my_str_set.pop())
print(my_str_set.pop())
print(my_str_set.pop())
```

```python
print(hash(1)) # 1
print(hash(1)) # 1
print(hash('a')) # -5092145942755...
print(hash('a')) # -5092145942755...
```

---

## hashable

- hash() 함수에 넣어 해시 값을 구할 수 있는 객체
- 대부분 불변 타입은 해시 가능
    - ex) int, float, str, tuple
- 가변형 객체는 해시 불가능
    - ex) list, set, dict
    - 값이 변하면 해시 값도 달라질 수 있어 테이블 무결성이 깨짐

```python
print(hash(1))
print(hash(1.0))
print(hash('1'))
print(hash((1, 2, 3)))

# TypeError: unhashable type: 'list'
print(hash((1, 2, [3, 4])))
```

---

### hashable과 불변성 간의 관계

- 해시 테이블에는 hashable만 저장 가능
- 불변 객체는 생성 후 값 변경이 불가능해, 항상 같은 해시 값 유지
- 내장 자료형 기준에서는 불변이어야 해시 가능

---

### 가변 객체는 왜 hashable하지 않을까

- **해시 값의 불변성**
    - 해시 테이블은 객체의 해시 값을 이용해 데이터를 저장하고 검색할 위치(인덱스) 결정
- **문제 발생**
    - list와 같은 가변 객체를 키로 사용하고, 그 리스트 내용을 변경하면 해시 값도 함께 변함
- **데이터 손실**
    - 데이터를 저장했던 인덱스, 변경 후 찾으려는 인덱스가 달라져 해당 데이터 영원히 찾기 X

→ 해시 테이블의 안정적인 동작을 보장하기 위해, 가변 객체의 해시 값 계산 허용 X

---

## hashable 객체가 필요한 이유

1. 해시 테이블 기반 자료 구조 사용
- set의 요소, dict의 키
- 중복 방지 & 빠른 검색, 조회

1. 불변성을 통한 일관된 해시 값
- 한 번 해시 값이 정해지면 바뀌지 않아야 해서 테이블 무결성 유지

1. 안정성과 예측 가능성 유지
- 동일한 데이터는 항상 동일한 해시 값 반환 → 로직을 단순화

---

### 해시 테이블 요약

- 해시 값을 인덱스로 삼아 데이터를 저장, 검색
- set은 순서가 없고, pop() 시 어떤 요소가 반환될 지 정해져 있지 않음
- dict는 삽입 순서는 보장되지만, 내부 구현은 여전히 해시 테이블
- 정수 / 문자열 등 타입에 따라 다르게 동작, 문자열 해시 시 난수화로 실행마다 달라질 수 있음
- hashable 객체만 set, dict의 키로 사용 가능 → 일반적으로 불변 타입

---

# 파이썬 문법 규격

### BNF ( Backus-Naur Form )

- 프로그래밍 언어의 문법을 표현하기 위한 표기
- 서로 다른 프로그래밍 언어, 데이터 형식, 프로토콜 등의 문법을 통일하여 정의하기 위

### EBNF ( Extended Backus-Naur Form )

- 메타 기호를 추가하여 더 간결하고 표현력이 강해진 형
- [  ] : 선택적 요소
- { } : 0번 이상 반복
- ( ) : 그룹