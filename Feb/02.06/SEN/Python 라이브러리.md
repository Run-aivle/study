# Python 라이브러리

# 1. 데이터 구조 🌟

---

- CRISP-DM(Cross-Industry Standard Process for Data Mining)
    
    업무 이해(문제 정의, 정보 도출) → 데이터 이해 → 모델링을 위한 데이터 구조 준비(전처리) → 모델링 → 평가(학습, 검증) → 배포
    

## 분석할 수 있는 데이터

### 데이터 종류

**범주형** - 질적 데이터(정성적 데이터)

ex) 월 데이터 (3월의 1월의 3배가 아니기 때문에)

1. 명목형 데이터 - 그룹으로 묶을 수 있는 데이터
    
    ex) 성별, 시도, 흡연여부
    
2. 순서형 데이터 - 범주 + 순서
    
    ex) 연령대, 매출등급
    

**수치형** - 양적 데이터(정량적 데이터)

ex) 3개월(1개월의 3배)

1. 이산형 데이터 - ex) 판매량, 매출액, 나이
2. 연속형 데이터 - ex) 몸무게, 온도

<aside>
💡 날짜는 범주형과 수치형 데이터가 아님

</aside>

### 데이터가 가지는 구조

**기본구조: 2차원**

- Table, 2차원 Array, DataFrame

① 열, 정보, 변수, 요인(Feature, X , input, 독립변수), 결과(Target, y, output, Label, 종속변수)

② 행, **분석단위**, 샘플, 관측치, 데이터 건수

![Untitled](Python%20%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%87%E1%85%B3%E1%84%85%E1%85%A5%E1%84%85%E1%85%B5%203cd7c2f1d2774163826ab230d7b5f12a/Untitled.png)

![Untitled](Python%20%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%87%E1%85%B3%E1%84%85%E1%85%A5%E1%84%85%E1%85%B5%203cd7c2f1d2774163826ab230d7b5f12a/Untitled%201.png)

![Untitled](Python%20%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%87%E1%85%B3%E1%84%85%E1%85%A5%E1%84%85%E1%85%B5%203cd7c2f1d2774163826ab230d7b5f12a/Untitled%202.png)

# 2. Numpy

---

- **리스트**
    - 값의 집합(collection)
    - 다른 타입의 데이터도 한꺼번에 저장 가능
    - 요소 변경, 추가, 제거가 용이함
    - 수학적 계산이 느리고 데량의 데이터 처리 속도 느림 - numpy 사용
    
    **리스트와 numpy의 차이**
    
    - numpy.array는 다양한 수학적 계산 가능 → list로 만든 뒤 numpy.array로 계산
    - list는 다른 자료형 넣기 가능, array는 같은 자료형만 가능
    - list는 콤마, array는 콤마 없음

**Numpy**

- 수치 조사, 자료 조사에 사용하는 데이터
- 수치적 관점 데이터

**라이브러리/패키지?**

- 이미 만들어진 함수들을 묶어놓은 것

```python
import 라이브러리 
```

## 배열 만들기

- 용어 정리
    - Axis: 배열의 각 축
    - Rank: 축의 개수(차원)
    - Shape: 축의 길이, element의 갯수

```python
arr = np.array([1,2,3,4,5])
```

- **Axis 0의 의미**🌟
    - 분석 단위를 구성(분석 단위의 개수)
    - 3차원 데이터, (2500, 28, 28)은 28*28 이미지가 2500장

- ndim 차원 확인
    
    ```python
    arr.ndim
    ```
    
- shape 형태(크기) 확인:
    - 배열 형태를 확인
    - 튜플로 표시
    
    ```python
    arr.shape
    ```
    
- dtpye 요소 자료형 확인:
    - 배열에 포함된 요소들의 자료형을 확인
    - 배열은 한가지 자료형만 가질 수 있다.
    
    ```python
    arr.dtype
    ```
    
- reshape 차원 변환:
    - 배열의 곱(전체 사이즈)의 약수만 가능
    - reshape(a, -1) 열은 마음대로 정해줌
    
    ```python
    b1.reshape(a,b)
    ```
    

### 함수와 매서드

- 메서드 : 리스트. sum(), array.___  특정변수(데이터, 오브젝트)에 딸려 있는 함수 특정 자료형이여야만 가능, 선언해줘야만 사용 가능
- 함수: np.sum(), 어떤 자료형이든 가능

## 배열 인덱싱과 슬라이싱

- 1차원: 축이 하나
- 2차원 이상: 축이 여러개

### 인덱싱

- arr[행 인덱스, 열 인덱스]
- arr[행 인덱스][열 인덱스]
- arr[행 인덱스] : 특정 행 전체
- arr[:, 열 인덱스] : 특정 열 전체
- a[범위, 값] → 1차원
- a[값, 범위] → 1차원
- a[범위, 범위] → 2차원

```python
a = np.array([[1,2,3],
							[4,5,6],
							[7,8,9]])
print(a[1,2])  #6
print(a[1][2])  #6
print(a[[1,2,0],[2, 0, 1]])  # [6 7 2]
print(a[[1],[2]])  #[6]
print(a[[1,2],[3]])
print(a[:, 1]) #[2 5 8]

# 2차원으로 출력
print(a[:, [1]])  #[[ 2][ 5][ 8][11]]
print(a[[1,2]]) # [[4 5 6][7 8 9]]
print(a[1], :]) # [[4 5 6][7 8 9]]
print(a[1:2, :]) # [[4 5 6][7 8 9]]
```

### 슬라이싱

- 배열[:,:]형태로 지정해 그 위치의 요소를 조회
- 2차원 배열

```python
a = np.array([[1,2,3],
							[4,5,6],
							[7,8,9]])
print(a[0:2]) # [[1 2 3][4 5 6]]
print(a[0, 0:2]) # [1 2]
print(a[0:3, 1:3])  # [[2 3][5 6][8 9]]
print(a[:, 1:2]) # [[2][5][8]
```

### 불리안 방식(조건) 배열 인덱싱

- 조건에 맞는 요소를 선태하는 방식
- 조건문
    - =, >, < emddmfh qlrygks rnans
    - 결과: Boolean True or False

```python
print(scpre[score >= 90])
```

## 배열 연산

- 배열 사이의 더하기, 빼기, 곱하기, 나누기
1. 배열 더하기 
    
    + 또는 np.add(x,y)
    
2. 배열 빼기
    
    - 또는 np.subtract(x,y)
    
3. 배열 곱하기
    
    * 또는 np.multiply(x,y)
    
4. 배열 나누기 
    
    / 또는 np.devide(x,y)
    
5. 배열 제곱
    
    ** 또는 np.power(x,y)
    
6. 배열 집계
    - axis = 0: 열 기준 집계
    - axis = 1: 행 기준 집계

# 3. Pandas

---

- 비즈니스 관점 데이터
- 익숙한 표 형태로 데이터를 다룸

## 데이터 프레임 생성

### 데이터 프레임이란?

데이터 분석에서 가장 중요한 데이터 구조

- 관계형 데이터베이스의 테이블 또는 엑셀 기트와 같은 형태(2차원 구조)
- 변수들의 집합 → 각 열을 변수라고 부름
- 열(정보, 변수, feature, target), 행(분석단위, 관측치, 샘플)
- 여러 시리즈들을 합한 것

**시리즈란?**

- 하나의 정보에 대한 데이터들의 집합
- 데이터 프레임에서 하나의 열을 떼어낸 것(1차원)

### 데이터 프레임 불러오기

1) csv 파일로 가져오기

2) url로 가져오기

## 데이터 프레임 탐색

```python
# 상위 데이터 확인
data.head()
# 하위 데이터 확인
data.tail()
# 크기 확인
data.shape

# 열확인
data.colums
data.colums.values
list(data)

# 자료형 확인
data.dtypes  #열 자료형 확인
data.info()  #열 자료형, 값 개수 확인

#기초통계정보
data.describe()

# 정렬해서 보기
data.sort_valeus('행', ascending = False) # false는 내림차순
data.sort_valeus(['A', 'B'], ascending = False)

# 기본 집계
data['A행'].unique()   #고유값 확인
data['A행'].value_counts()   #고유값과 개수 확인
data['A행'].mean()
data[['A', 'B']].max()
data['A행'].min()
data['A행'].median()
data['A행'].sum()
np.sum(arr, axis = 0)  # 열기준 집계
np.sum(arr, axis = 1)  # 행기준 집계
```

### 특정 열 조회

- df.loc[:,[열 이름1, 열 이름2, ….]]
- df[[열 이름1, 열 이름2]]
- 1차원 조회

```python
tips['total_bill']   # ----> 결과값: Series
tips.total_bill
```

- 2차원 조회

```python
tips[['total_bill']]  # ---> 결과값: DataFrame
```

### 조건으로 조회

- df.loc[조건] 형태로 조건을 지정해 조건에 만족하는 데이터만 조회 가능
- 단일 조건 조회
    
    ```python
    data[data['A 행'] > 10]]
    ```
    
- 여러 조건 조회
    - and와 or 대신에 & 와 |를 사용
    - 조건들은 (조건)&(조건)형태로 괄호를 사용
    
    ```python
    data.loc[(data['A행']> 10) & ( data['B행'] < 350)]
    ```
    
- isin() - isin(값1, 값2, ….. n) : 값1 또는 값2 또는 값 n인 데이터만 조회
- between(값1, 값2): 값1~값2까지 범위안의 데이터만 조회
- 조건에 만족하는 행의 일부 열 조회
    
    ```python
    data.loc[data['A행'] >=10 ]['B행', 'C행',....]
    ```
    
- data.loc[값1:값2]: loc다음 숫자가 오는 경우 값1 ~ 값2까지

## 데이터 프레임 집계

### Groupby()

- dataframe.groupby(’집계기준변수, as_index =)[’집계대상변수’].집계함수
    - 집계기준변수 : ~별에 해당되는 변수 혹은 리스트. 범주형 변수
    - 집계대상변수: 집계함수로 집계할 변수 혹은 리스트

```python
df.groupby('a', as_index=False)[['b','c,']].sum()

# a별 나머지 열들 합계 조회
df.groupby('a', as_index=False).sum() 

# 집계 기준 열을 여럿 설정 가능
df.groupby(['a','b'], as_index = False).sum()
```

**agg():** 

- **열 하나에 대해 합계, 평균 등의 집계를 한 번에 수행 가능**
    
    

---

# 명령어&Tips

- np.zeros() : 0으로 채워진 배열
- np.ones() : 1로 채워진 배열
- np.full() : 특정 값으로 채워진 배열
- np.eye() : 정방향 행렬
- np.random.random() : 랜덤 값으로 채운 배열
- np.where(조건, 0, 1): 조건문에 일치하는 경우 0을 반환, 일치하지 않는 경우 1을 반환
- np.argmax(): 가장 큰(작은) 값의 인덱스 변환
- np.argmin(): 가장 작은 값의 인덱스 변환
- 딕셔너리{키: 값, 키: 값, ….}: 값에는 리스트가 올 수도 있고, 또 다른 딕셔너리가 될 수도 있음