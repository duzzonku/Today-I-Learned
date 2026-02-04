# 2차원 List

과목명: 알고리즘
작성일: 2026년 2월 4일

# 2차원 리스트

## 2차원 배열의 선언

- 1차원 List를 묶어놓은 List
- 2차원 이상의 다차원 List는 차원에 따라  Index를 선언
- 2차원  List의 선언 : 세로 길이 (행의 개수), 가로 길이(열의 개수)를 필요로 함
- 데이터 초기화를 통해 변수 선언과 초기화 가능

---

### 입력을 2차원 배열에 저장

```python
n = int(input())
arr = [list(map(int, input().split())) for _ in ragne(N)]
```

---

### 0으로 채워진 3*4 배열 만들기

```python
arr = [[0] * 4 for _ in range(3)]
```

---

## 배열 순회

- n * m 배열의 n*m개의 모든 원소를 빠짐없이 조사하는 방법

---

## 행 우선 순회

```python
# i 행의 좌표
# j 열의 좌표

for i in range(n):
		for j in range(m):
				f(array[i][j])
```

---

### n * m 배열의 크기와 저장된 값이 주어질 때 합을 구하는 방법

```python
n, m = map(int, input().split())
arr = [list(map(int, input().split())) for _ in range(n)]

sum = 0

for i in range(n):
		for j in range(m):
				sum += arr[i][j]
```

---

## 열 우선 순회

```python
for j in range(m):
		for i in range(n):
				f(array[i][j]) 
```

---

## 지그재그 순회

```python
for i in range(n):
		for j in range(m):
				f(array[i][j + (m-1-2*j) * (i%2)])
```

---

## 델타를 활용한 2차원 배열 탐색

- 2차 배열의 한 좌표에서 4 방향의 인접 배열 요소를 탐색하는 방법

---

### 인덱스 (i, j)인 칸의 상하좌우 칸 (ni, nj)

```python
di[] = [0, 1, 0, -1]
dj[] = [1, 0, -1, 0]

for k : 0 -> 3
		ni = i + di[k]
		nj = j + dj[k]
```

---

### 2차원 배열의 한 좌표에서 4 방향의 인접 배열 요소를 탐색하는 방법

```python
#방법 1
n = 3
m = 4

di = [0, 1, 0, -1]
dj = [1, 0, -1, 0]

for i in range(n):
		for j in range(m):
				for d in range(4):
						ni = i + di[d]
						nj = j + dj[d]
						if 0 <= ni < n and 0 <= nj < n: # 유효범위 확인
								f(arr[ni][nj]
```

```python
# 방법 2

for i in range(n):
		for j in range(m):
				for di, dj in [[0,1], [1,0], [0,-1], [-1,0]]:
						ni, nj = i + di, j + dj
						if 0 <= ni < n and 0 <= nj < n: # 유효범위 확인
								f(arr[ni][nj]
```

---

### n * n 배열에서 각 원소를 중심으로, 상하좌우 k칸의 합계 중 최댓값 (k=2)

```python
max_v = 0
for i in range(n):
		for j in range(m):
				s = arr[i][j]
				for di, dj in [[0,1],[1,0],[0,-1],[-1,0]]: # 각 방향
						for c in range(1, k+1): # 거리 별
								ni, nj = i+di*c, j+dj*c
								if 0<= ni N n and 0 <= nj < n:
										s += arr[ni][nj]
				if max_v < s:
				max_v = s
```

---

### 전치 행렬

```python
# i : 행의 좌표, 행의 크기 len(arr)
# j : 열의 좌표, 열의 크기 (len(arr[0])

arr = [[1,2,3],[4,5,6],[7,8,9]] 

for i in range(3):
		for j in range(3):
				if i < j:
						arr[i][j] , arr[j][i] = arr[j][i], arr[i][j]ㅑ
```

---

### i, j의 크기에 따라 접근하는 원소 비교

- i == j ( 왼쪽 대각선 )

```python
for i in range(n):
		f(arr[i][j])
```

- N-1-i == j ( 오른쪽 대각선 )

```python
for i in range(n):
		f(arr[i][n-1-i])
```

---

## 부분집합

### 부분집합 합 문제

- 유한 개의 정수로 이루어진 집합이 있을 때, 이 집합의 부분집합 중에 조건에 맞는 경우를 찾는 문제

---

### 각 원소가 부분집합에 포함되었는지를 loop를 이용하여 확인하고 부분집합 생성

```python
bit = [0,0,0,0]
for i in range(2):
		bit[0] = i
		for j in range(2):
		bit[1] = j
				for k in range(2):
						bit[2] = k
								for l in range(2):
										bit[3] = l
										print_subset(bit)
```

---

## 비트 연산자

- & : 비트 단위로 AND 연산
- | : 비트 단위로 OR 연산
- << : 피연산자의 비트 열을 왼쪽으로 이동
- >> : 피연산자의 비트 열을 오른쪽으로 이동

---

### << 연산자

- 1<<n : 2^n
- 원소가 n개일 경우 모든 부분집합의 수를 의미

---

### >> 연산자

- i & (1<<j)
- i의 j번째 비트가 1인지 아닌지를 검사
