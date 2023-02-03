# Python 프로그래밍

# 알고리즘 기초

## 알고리즘과 플로우 차트

---

**알고리즘**

- 알고리즘을 짤 때 다양한 경우에 원하는 값으로 작동되는지 확인하는 작업 필요
- 어떠한 문제를 해결하기 위해 정해 놓은 일련의 절차
- 올바른 알고리즘 : 어떠한 경우에도 맞게 나오는 알고리즘

### 조건문과 분기

분기는 프로그램의 실행 흐름을 다른 곳으로 변경하는 명령을 뜻하며, 조건문을 충족 여부에 따라 프로그램이 분기하게 됨

![Untitled](Python%20%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20edbf43b08f91479fa021c6c00bb75764/Untitled.png)

## 반복하는 알고리즘

- While 문

```python
While i < n:
	sum += i
	i += 1
```

- For 문

```python
for i in range(1, n+1):
	sum += i
```

> 명령어/ 함수
> 
- Input() : 입력받은 값은 문자열 type으로 반환 되므로 int()를 사용하여 정수형으로 형 반환을 해야함
- Int(): 정수형으로 변환

- 최댓값 구하기
    
    ```python
    maximum = a
    if b > maximum:
    	maximum = b
    if c > maximum:
    	maximum = c
    ```
    

## 반복하는 알고리즘

---

### 무한 루프와 break

- 조건이 만족하면 루프를 탈출(break)
- break는 완전히 루프를 벗어나는 것
- 코드
    
    ```python
    while True:
    	n = int(input('n값을 입력하세요.: '))
    	if n > 0:
    		break # n이 0보다 커질때 까지 반복
    ```
    

### continue와 break

- break는 루푸를 완전히 탈출
- continue는 실행하지않고, 다음으로 진행
- 코드
    
    ```python
    for i in range(1, area + 1):
    	if i * i > area: break 
    	if area % i: continue
    print(f'{i} x {area // i}')
    ```
    

### 다중 루프(multi loop)

- 반복문 안에 다시 반복문이 존재하는 경우
- 코드
    
    ```python
    # 구구단
    for i in range(1,10):
    	for j in range(1,10):
    		print(f'{i*j :3}, end='') # 3가지로 출력값 출력
    	print()
    ```
    

# 자료 구조

- 논리적인 관계로 이루어진 데이터 구성
- 데이터가 모여있는 구조

## 자료구조와 배열

---

- 논리적인 관계로 이루어진 데이터 구성
- 데이터가 모여있는 구조

### t**uple()**

- 원소의 값을 변경할 수 없는 리스트
- 리스트가 쓸 수 있는 함수와 튜플이 쓸 수 있는 함수가 차이가 있음

```python
t1 = (1,2,3)
t[0] = 5   # Error
```

### 역순으로 정렬하기

```python
def reverse_list(a):
	n = len(a)
	for i in range(n // 2):
		a[i], a[n - i - 1] = a[n - i - 1], a[i]
```

## 검색 알고리즘

---

- 원하는 값을 가진 원소를 찾아내는 알고리즘
- 선형 검색과 이진 검색 방안
- 자료구조에 따라 검색하는 알고리즘이 달라짐

### 선형 알고리즘(linear search)

- 직선 모양으로 늘어선 리스트에서 검색하는 경우에 원하는 값을 가진 원소를 찾을 때까지 맨 앞부터 스캔하여 순서대로 검색하는 알고리즘
- 검색 성공: 검색할 값과 같은 원소를 찾은 경우
- 검색 실패: 검색할 값과 같은 원소를 찾지 못하고 리스트의 맨 끝에 도달한 경우

```python
i = 0
while True:
	if i -- len(a):
		#검색실패
	if a[i] == key:
		# 검색 성공(찾은 원소의 인덱스 i)
```

- while 문
    - while 문 선형 검색에서는 아래처럼 두가지를 언제나 체크해야함(if 문 두개)
    - 선형검색의 종료 조건
        1. 검색 성공: 검색할 값과 같은 원소를 찾은 경우
        2. 검색 실패: 검색할 값과 같은 원소를 찾지 못하고 리스트의 맨 끝에 도달한 경우
    
    ```python
    def seq_search(a, key):
    	i = 0
    	while True:
    		if i ==len(a)
    			return -1
    		if a[i] == key:
    			return i
    		i+=1
    ```
    
    **보초법(Sentienl method)**
    
    - 보초법을 사용하는 경우 검색에 무조건 성공하는데 찾은 값이 보초인지 아닌지만 확인함
    - 선형 검색(보초법)의 종료 조건
        1. 검색할 값과 같은 원소를 찾은 경우 —> 스캔 종료
        2. ~~검색 실패: 검색할 값과 같은 원소를 찾지 못하고 리스트의 맨 끝에 도달한 경우~~
        3. 스캔 종료 후 검색값과 원소를 찾은 위치가 보초의 위치 인지만 판단
    
    ```python
    def seq_search(b, key):
    	a = b.copy()
    	a.append(key)
    	
    i = 0
    	while True:
    		if a[i] == key:
    			break
    		i+=1
    
    	return -1 if i == len(b) else i
    ```
    
- for 문
    
    ```python
    def seq_search(a, key):
    
    	for i in range(len(a)):
    		if a[i] == key:
    			return i
    		return -1
    ```
    

### 이진 검색(Binary search)

- 이진 검색은 리스트의 데이터가 오름차순이나 내림차순으로 정렬되어 있어야 적용 가능
- 이진 검색은 선형 검색에 비해 빠르게 검색 값을 찾을 수 있음
- a[pc] == key이면 검색 성공
- a[pc] < key: pc에서 오른쪽으로 한 칸 이동하여 새로운 왼쪽 끝 pl로 지정하고, 검색 범위를 뒤쪽 절반으로 좁힘
- a[pc] > key: pc에서 왼쪽으로 한칸 이동하여 새로운 오린쪽 끝  pr로 지정하고, 검색 범위를 앞쪽 절반으로 좁힘
- a[pr]과 a[pl]위치가 바뀌게 되는 경우
- 종료 조건:
    1. a[pc] 와 key가 일치하는 경우
    2. 검색 범위가 더 이상 없는 경우

```python
def bin_search(a,key):
	pl=0
	pr = len(a) -1
	while True:
		pc = (pl+pr) // 2
		if a[pc]==key:
			return pc
		elif a[pc]< key:
			pl = pc +1
		else:
			pr = pc -1
		
		if pl > pr:
			break

	return -1
```

# 명령어 & Tips

---

- int() : 정수로 변환
- end = ‘’는 줄바꿈을 하지 않는 것
    
    ```python
    print(a, end = '')
    ```
    
- a,b = b,a
    - 우변의 b,a에 의해 두 값을 압축한 튜플 생성
    - 대입할 때 튜플 (b,a)를 풀어서 b,a로 만든 다음 각각 a와 b에 대입
    
    ```python
    if a>b:
    	a,b = b,a  # b<a로 바꿔주는 식
    ```
    
- if a% i : —> 나머지가 존재하는지 확인하는 조건문
- 문자열은 알파벳 순서대로 순서가 커짐
- append() : 리스트에 원소추가
- enumerate() : 인덱스와 원소를 짝지어서 튜플로 꺼내는 내장 함수