# np.array, np.arange 외 다른 생성 함수 (creation function)   
## zeros - `np.zeros(shape, dtype)`   
### 0으로 가득찬 ndarray 생성   

```python
import numpy as np
np.zeros(shape=(10,), dtype = np.int8) # 10 zero vector 셍성
np.zeros((2,5))  # 2 by 5 - zero matrix 생성
```

### 결과
```
array([0,0,0,0,0,0,0,0,0,0], dtype=int8)
array([[0., 0., 0., 0.,],
      [0., 0., 0., 0.,]])
```
## ones - `np.ones(shape, dtype)`   
### 1로 가득찬 ndarray 생성
```python
np.ones((2,5))
m1=np.ones(shape=(4,5), dtype='int32') # 기본타입이 float 임
```

### 결과
```
array([[1., 1., 1., 1., 1.,],
      [1., 1., 1., 1., 1.,]])
array([[1, 1, 1, 1, 1],
       [1, 1, 1, 1, 1],
       [1, 1, 1, 1, 1],
       [1, 1, 1, 1, 1]], dtype=int32)
dtype('int32')
```
## random.uniform - `np.random.uniform(low,high,size)`
### 주어진 범위의 uniform distribution 에서 랜덤으로 실수를 생성함   
### `low` : 시작(포함 O)    
### `high` : 끝(포함 X)    
### `size` : shape (default : single value)
```python
m2=np.random.uniform(3,5,size(2,3))
m2
```

### 결과
```
array([[3,36044285, 4.68076162, 3.92564691],
      [3.02549194, 4.39847917, 3.30482479]])
```

## random.normal - `np.random.normal(loc,scale,size)`
### 주어진 normal distribution 에서 랜덤으로 실수를 생성함
### `loc`: `평균` (default: 0.0)
### `scale`: `표준편차` (default: 1.0)
### `size`: `shape` (default: single value)

```python
m1=np.random.normal(2,5) #(평균 ,표준편차)
m1
m2=np.random.normal(size=(2,5))
m2
m3=np.random.normal(10,10,size=(2,5))
m3
```

### 결과
```
2.898258378189886
array([[ 0.29082834, -2.03795133, -0.41840466, -0.84501359, -1.15271194],
       [-1.09066577, 0.21069615, 0.51302339, -0.21331125, 0.37419426]])
array([[-10.35607991, 12.5696705 , 2.85461204, 18.09154594,16.21204834],
       [13.15010858, 25.97834317, 7.17524937, 13.43622399,11.83359251]])
```
## random.choice - `np.random.choice(a, size, replace)`
### 주어진 array에서 랜덤하게 element를 choice 함
### `a`: 랜덤하게 추출할 array   
### `size`: shape (default: single value)   
### `replace`: 복원 여부 (default: True, 복원추출)   

```python
np.random.choice([1,2,3,4,5], size=(2,3))
np.random.choice([1,2.1], size=(2,3))
np.random.choice(np.arange(10), size=(2,3), replace=False)
np.random.choice(np.arange(10), size=(2,3))
```
### 결과
```
array([[1, 1, 1],
       [1, 2, 4]])
array([[2.1, 1. , 1. ],
       [1. , 2.1, 2.1]])
array([[4, 6, 9],
       [2, 0, 5]])
array([[4, 4, 1],
       [8, 9, 7]])
```
## matplotlib hist 
### - ndarray의 데이터를 히스토그램으로 나타내기
### - matplotlib의 hist 함수 사용 - `import matplotlib,pyplot as plt`

```python
fig=plt.figure(figsize=(5,3), dpi=100) # 액자 틀 생성
ax=fig.subplots() # 도화지 생성
ar1=np.random.normal(0,10,10000) # 평균이 0, 표준편차가 10인 실수 1000개를 생성
_=ax.hist(ar1,bins=20,edgecolor='r') # 도화지에 hist plot 수행
# 매개변수 생성 하지않고 _ 로 저장하기 (plot만 보기)
```
### 결과


## indexing
## vector
```python
ar1=np.arange(1,4)
print(ar1)
print(ar1[1])
print(ar1[-1])
```
### 결과
```
[1 2 3]
2
3
```
## matrix
```python
print("# 1)")
a1=np.arange(24).reshape(4,6)
a1[2:, 1:4] # 2번째 행부터 끝까지, 1~3열까지 인덱싱

print("# 2)")
m1=a1
m1
m1[2:4,1:4]=[[-1,-2,-3],[-4,-5,-6]] # 2~3행까지, 1~3열까지를 [-1,-2,-3],[-4,-5,-6] 로 대체
```
### 결과
```
# 1)
array([[13, 14, 15],
      [19, 20, 21]])
# 2)
array([[ 0, 1, 2, 3, 4, 5],
       [ 6, 7, 8, 9, 10, 11],
       [12, -1, -2, -3, 16, 17],
       [18, -4, -5, -6, 22, 23]])
```
## tensor 
```python
ar2=np.arange(60).reshape(6,2,5)
ar2[4,0,4]=1000 # 4번째 0행 4열을 1000으로 대체
ar2
```
### 결과
```
array([[[ 0, 1, 2, 3, 4],
        [ 5, 6, 7, 8, 9]],
       [[ 10, 11, 12, 13, 14],
        [ 15, 16, 17, 18, 19]],
       [[ 20, 21, 22, 23, 24],
        [ 25, 26, 27, 28, 29]],
       [[ 30, 31, 32, 33, 34],
        [ 35, 36, 37, 38, 39]],
       [[ 40, 41, 42, 43, 1000],
        [ 45, 46, 47, 48, 49]],
       [[ 50, 51, 52, 53, 54],
        [ 55, 56, 57, 58, 59]]])
```
## slicing (vector)
```python
ar1=np.arange(10)
print(ar1)
print(ar1[:])
print(ar1[:4])
print(ar1[2:])
```
### 결과
```
[0 1 2 3 4 5 6 7 8 9]
[0 1 2 3 4 5 6 7 8 9]
[0 1 2 3]
[2 3 4 5 6 7 8 9]
```
## slicing (matrix)
```python
ar1 = np.arange(15).reshape(3,5)
print(ar1[:,2:])
print(ar1[1:3])
```
### 결과
```
[[ 2 3 4]
 [ 7 8 9]
 [12 13 14]]

 [[ 5 6 7 8 9]
  [10 11 12 13 14]]
```
### fancy index
# operation functions (sum, max, argmin, mean, ...)
## sum (ndarray element들의 합)
```python
v1=np.arange(1,11)
v1
np.sum(v1)
v1.sum()
```
### 결과
```
array([1,2,3,4,5,6,7,8,9,10])
55
55
```
## sum with axis parameter
## axis: operation function을 실행할 때, 기준이 되는 축
## axis = 0 행값들을 열에 대해 더하기 (세로)
## axis = 1 열값들을 행에 대해 더하기 (가로)
```python
m1=np.arange(1,13).reshape(3,4) 
m1
np.sum(m1, axis=0)
np.sum(m1, axis=1)
```
### 결과
```
array([[1,2,3,4],
       [5,6,7,8],
       [9,10,11,12]] )
78
array([15,18,21,24])
array([10,26,42])
```
## 3차원 tensor
```python
ar1=np.arange(12).reshape(2,3,2)
ar1
ar1[0,2,1] # 0번째 행렬에 2번째 행에 1번째 열
ar1[0][2][1]
```
### 결과
```
array([[[ 0, 1],
        [ 2, 3],
        [ 4, 5]],

        [[ 6, 7],
         [ 8, 9],
         [10, 11]]])
5
5
```
```python
m1=np.arange(1,13).reshape(3,4)
m1
# mean
np.mean(m1,axis=1)
m1.mean(axis=1)
# median
np.median(m1,axis=0)
```
```
array([[ 1, 2, 3, 4],
       [ 5, 6, 7, 8],
       [ 9, 10, 11, 12]])
array([ 2.5, 6.5, 10.5])
array([ 2.5, 6.5, 10.5])
array([5., 6., 7., 8.])
```
## std & variance
```python
m1=np.arange(12).reshape(3,4)
m1
# std
m1.std(axis=1)
np.std(m1, axis=1)
# variance
m1.var(axis=0)
np.var(m1, axis=0)
```
### 결과
```
array([[ 0, 1, 2, 3],
[ 4, 5, 6, 7],
[ 8, 9, 10, 11]])
array([1.11803399, 1.11803399, 1.11803399])
array([1.11803399, 1.11803399, 1.11803399])
array([10.66666667, 10.66666667, 10.66666667, 10.66666667])
array([10.66666667, 10.66666667, 10.66666667, 10.66666667])
```
## max & min
```python
a1=np.random.randint(100, size=(3,4))
a1
# min
np.min(a1)
np.min(a1, axis=0)
# max
np.max(a1)
np.max(a1, axis=0)
```
### 결과
```
array([[10, 22, 83, 88],
       [44, 74, 98, 45],
       [46, 90, 48, 83]])
10
array([10, 44, 46]) # axis=0, 세로
98
array([10, 22, 83, 88]) # axis=1, 가로
```
## argmax & argmin
`argmax` : 최대값이 있는 곳 index / `argmin` : 최소값이 있는 곳 index
```python
m1=np.random.randint(100, size=(3,4))
m1
# argmin
np.argmin(m1)
np.argmin(m1.flatten())
np.argmin(m1,axis=1) # 전체에서 가장 작은 값 11 → flatten하면 위치는 8번째
# argmax
np.argmax(m1,axis=0) 
```
### 결과
```
array([[73, 39, 35, 79],
       [45, 21, 35, 28],
       [11, 77, 58, 71]])
8
8
array([2, 1, 0])
array([0, 2, 2, 0])
```
