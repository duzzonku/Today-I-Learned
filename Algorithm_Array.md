# 순열

과목명: 알고리즘
작성일: 2026년 2월 12일

## 단순하게 순열을 생성하는 방법

- 동일한 숫자가 포함되지 않았을 때, 각 자리 수 별로 loop를 이용해 표현할 수 있다

```python
for i1 in range(1, 4):
		for i2 in range(1, 4):
				if i2 != i1:
						for i3 in range(1, 4):
								if i3 != i1 and i3 != i2:
										print(i1, i2, i3)
```

## Backtracking을 이용하여 {1,2,3, … , NMAX}에 대한 순열 구하기 1

```python
def backtrack(a, k, n):
		c = [0] * MAXCANDIDATES
		
		if k == n:
				process_solution(a, k)
				
		else:
				ncandidates = construct_candidates(a, k, n, c):
				for i in range(ncandidates):
						a[k] = c[i]
						backtrack(a, k+1, n)
						
						
def construct_candidates(a, k, n, c):
    # [1] 사용 여부 체크 배열 (in_perm) 초기화
    # 1~N까지 숫자의 사용 여부를 체크하기 위해 NMAX+1 크기로 만듭니다.
    in_perm = [False] * (NMAX + 1)
    
    # [2] 지금까지(0 ~ k-1) 사용한 숫자는 True로 체크
    for i in range(k): 
        used_num = a[i]       # 앞 단계에서 선택한 숫자
        in_perm[used_num] = True # "이 숫자는 이미 썼어요!" 표시

    # [3] 아직 안 쓴 숫자(False)만 골라서 후보(c)에 담기
    ncandidates = 0
    for i in range(1, NMAX + 1): # 1부터 3까지 확인
        if in_perm[i] == False:  # 아직 안 썼다면?
            c[ncandidates] = i   # 후보 리스트에 추가
            ncandidates += 1     # 후보 개수 증가
            
    return ncandidates # 찾은 후보의 개수 반환
			
			
			
def process_solution(a, k):
		for i in range(0, k):
				print(a[i], end=' ')
		print()
		

MAXCANDIDATES = 3
NMAX = 3
a = [0] * NMAX
backtrack(a, 0, 3)
```

---

# 가지치기

## 부분집합의 합

- A[i] 원소를 부분집합의 원소로 고려하는 재귀 함수 (A는 서로 다른 자연수의 집합)

```python
# A: 숫자 리스트, N: 개수
A = [i for i in range(1, 11)] # [1, 2, ..., 10]
N = 10
key = 55 # 찾으려는 합
cnt = 0  # 정답 개수

def f(i, N, s, t):
    global cnt, fcnt
    fcnt += 1 # 함수가 몇 번 호출됐는지 체크 (성능 확인용)
    
    # 1. [가지치기] 이미 합이 목표보다 커지면 그만둠 (Pruning)
    if s > t:
        return # 더 볼 필요 없으니 돌아가! (백트래킹)
        
    # 2. [정답] 목표 합에 도달하면 카운트
    if s == t:
        cnt += 1
        return # 남은 숫자 더 볼 필요 없이 종료

    # 3. [종료] 끝까지 다 봤는데도 답이 안 나왔으면 종료
    if i == k:
        return

    # 4. [재귀] 다음 단계로 (Include / Exclude)
    
    # (1) 이번 원소(A[i])를 더하고 가는 경우
    f(i + 1, k, s + A[i], t) 
    
    # (2) 이번 원소를 안 더하고 가는 경우
    f(i + 1, k, s, t)

# 실행
f(0, N, 0, key)
print(cnt)
```

### 추가 고려사항

- 남은 원소의 합을 다 더해도 찾는 값 T 미만인 경우 중단

---

# 순열 1

### A[1, 2, 3]의 모든 원소를 사용한 순열

- 3개의 칸에 넣을 수 있는 수를 나열
- 총 6가지 경우
- 자리 교환으로 순열 생성

```python
A = [1, 2, 3]
N = len(A)

def perm(k, n):
    # [종료 조건] k가 끝까지 도달했으면 출력 (하나의 순열 완성)
    if k == n:
        print(A)
        return

    # [재귀] k번째 자리에 들어갈 숫자를 결정 (k부터 n-1까지 교환)
    for i in range(k, n):
        # 1. 교환 (Swap): 결정 단계
        A[k], A[i] = A[i], A[k]
        
        # 2. 다음 자리 결정하러 감 (재귀)
        perm(k + 1, n)
        
        # 3. 복구 (Backtrack): 원래대로 돌려놓기
        A[k], A[i] = A[i], A[k]

# 실행
perm(0, N)
```
