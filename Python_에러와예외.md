# 에러와 예외

과목: python
작성일: 2026년 1월 29일

# 디버깅

## 버그

- 소트프웨어에서 발생하는 오류 또는 결함
- 프로그램의 예상된 동작과 실제 동작 사이의 불일치

---

## 디버깅

- 소프트웨어에서 발생하는 버그를 찾아 수정하는 과정
- 프로그램의 오작동 원인을 식별하여 수정하는 작업

---

### 디버깅 방법

1. print 함수 활용
- 특정 함수 결과, 반복/조건 결과 등 나눠서 생각
1. 개발 환경 등에서 제공하는 기능 활용
- breakpoint, 변수 조회
1. Python tutor 활용
- 단순 파이썬 코드인 경우

---

## 에러

- 프로그램 실행 중 발생하는 예외 상황
- ex) 리스트에 없는 값을 꺼내려고 할 때

---

## 내장 에러

- 예외 상황을 나타내는 예외 클래스
- ZeroDivisionError : 0으로 나눌 때
- FileNotFoundError : 없는 파일을 열 때 발생
- NameError : 지역 또는 전역 이름을 찾을 수 없을 때 발생
- TypeError : 타입 불일치 / 인자 누락 / 인자 초과 / 인자 타입 불일치
- ValueError : 연산이나 함수는 문제가 없지만 부적절한 값을 가진 이자를 받
- IndexError : 시퀀스 인덱스가 범위를 벗어남
- KeyError : 딕셔너리에 해당 키가 존재하지 않는 경우
- ModueNotFoundError : 모듈을 찾을 수 없을 때
- ImportError : import 하려는 이름을 찾을 수 없을 때
- KeyboardInterrupt : 사용자가 Ctrl+C 또는 Delete를 누를 때 발생
- IndentationError : 잘못된 들여쓰기와 관련된 문법 오류

---

### 문법 에러 (Syntax Error)

- 프로그램의 구문이 올바르지 않은 경우 발생
- ex) 오타, 누락, 문법적 오류

---

## 예외 처리

- 예외가 발생했을 때 프로그램이 비상적으로 종료되지 않고, 적절하게 처리할 수 있도록 하는 방법

### try

- 예외가 발생할 수 있는 코드 작성

### except

- 예외가 발생했을 때 실행할 코드 작성

### else

- 예외가 발생했을 때는 실행할 코드 작성

### finally

- 예외 발생 여부와 상관없이 항상 실행할 코드 작성

---

## try - except 구조

- try 블록 안에는 예외가 발생할 수 있는 코드 작성
- except 블록 안에는 예외가 발생했을 때 처리할 코드 작성
- 예외가 발생하면 try 블록을 빠져나와 해당 예외에 대응하는 except 블록 이동

```python
# try-except
try:
    result = 10 / 0
except ZeroDivisionError:
    print('0으로 나눌 수 없습니다.')

try:
    num = int(input('숫자를 입력해주세요: '))
except:
    print('그건 숫자가 아닙니다....')
```

---

### 복수 예외 처리

```python
# 복수 예외처리
try:
    num = int(input('100을 나눌 값을 입력하시오 : '))
    print(100 / num)
except (ValueError, ZeroDivisionError):
    print('제대로 입력해주세요.')

try:
    num = int(input('100을 나눌 값을 입력하시오 : '))
    print(100 / num)
except ValueError:
    print('숫자를 넣어주세요')
except ZeroDivisionError:
    print('0으로 나눌 수 없습니다.')
except:
    print('에러 발생')

```

---

## else & finally

- else 블록은 예외가 발생하지 않았을 때 추가 작업을 진행
- finally 블록은 예외 발생 여부와 상관없이 항상 실행할 코드 작성

```python
try:
    x = int(input('숫자를 입력하세요: '))
    y = 10 / x
except ZeroDivisionError:
    print('0으로 나눌 수 없습니다.')
except ValueError:
    print('유효한 숫자가 아닙니다.')
finally:
    print('프로그램이 종료되었습니다.')
```

---

## as 키워드

- 예외객체 : 예외가 발생했을 때 예외에 대한 정보를 담고 있는 객체
- except 블록에서 예외 객체를 받아 상세한 예외 정보 활용 가능

```python
my_list = []

try:
    number = my_list[1]
except IndexError as error:
    # list index out of range가 발생했습니다.
    print(f'{error}가 발생했습니다.')
```

---

## try-except 와 if-else

- try-except 와 if-else 함께 사용 가능

```python
my_dict = {
    'key': 'value',
}

# EAFP (Easier to Ask for Forgiveness than Permission)
try:
    result = my_dict['key']
    print(result)
except KeyError:
    print('Key가 존재하지 않습니다.')

# LBYL (Look Before You Leap)
if 'key' in my_dict:
    result = my_dict['key']
    print(result)
else:
    print('Key가 존재하지 않습니다.')

```

---

## EAFP : Easier to Ask to Forgiveness than Permission

- 예외처리를 중심으로 코드를 작성하는 접근 방식
- 일단 실행하고 예외 처리
- try - excpet

```python
my_dict = {
    'key': 'value',
}

# EAFP (Easier to Ask for Forgiveness than Permission)
try:
    result = my_dict['key']
    print(result)
except KeyError:
    print('Key가 존재하지 않습니다.')

```

---

## LBYL : Look Before You Leap

- 값 검사를 중심으로 코드를 작성하는 접근 방식
- 실행하기 전에 조건을 검사
- if - else

```python
my_dict = {
    'key': 'value',
}

# LBYL (Look Before You Leap)
if 'key' in my_dict:
    result = my_dict['key']
    print(result)
else:
    print('Key가 존재하지 않습니다.')
```

---
