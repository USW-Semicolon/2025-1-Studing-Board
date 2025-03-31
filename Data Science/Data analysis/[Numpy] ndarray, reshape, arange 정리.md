# Numpy
* Numerical Python   
* 파이썬의 고성능 과학 계산용 패키지   
* Matrix와 Vector와 같은 Array 연산의 사실상의 표준   

## Numpy 특징   
* 일반 리스트에 비해 빠르고, 메모리가 효율적임.   
* 반복문 없이 벡터화된 연산 가능   
* 수학적 계산: 벡터화된 연산은 수학적 계산(행렬 연산, 선형대수, 통계 계산 등)에서 매우 유용.    
* 데이터 분석 및 머신러닝: 대규모 데이터셋을 다룰 때 벡터화된 연산은 계산 속도를 크게 향상.


```python
import sys
print('python', sys.version)

import numpy as np
print('numpy', np.__version__)

import pandas as pd
print('pandas', pd.__version__)


# 결과 확인을 용이하게 하기 위한 코드
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = 'all' #중간 계산값이나 결과를 자동으로 확인할 수 있어 코드 실행 중간 결과를 바로 볼 수 있음.
```

### 결과
```
python 3.12.7 | packaged by Anaconda, Inc. | (main, Oct  4 2024, 08:22:19) [Clang 14.0.6 ]
numpy 1.26.4
pandas 2.2.2 
```
## ndarray 생성 및 속성
```python
import numpy as np

v1=np.array([1,2,3,4.1])  # ndarray 생성
v1

## cf list and dictionary
l1=[1,2,3,4.1]
l1
d1={'a':1, 'b':2.3}
d1
```

### 결과
```
array([1. , 2. , 3. , 4.1])
[1, 2, 3, 4.1]
{'a': 1, 'b': 2.3}
```
## vector (1차원)
```python
v1=np.array([1,2,3,4.1])
v1
v1.dtype # data type
v1.ndim  # 몇차원
v1.shape  # 형태 개수 (0,0)
v1.size   # 요소 총 개수
```
### 결과
```
array([1. , 2. , 3. , 4.1])
dtype('float64')
1
(4,)
4
```

## dtype 
```python
ar1=np.array([1,'2',3,4.1])
ar1
ar1.dtype

ar2=np.array([1,2,3,4.1])
ar2
ar2.dtype

ar3=np.array([1,2,3,4.1], dtype=int)
ar3
ar3.dtype

ar4=np.array([1.1,'2',3,4], dtype=float)
ar4
ar4.dtype
```
### 결과
```
array(['1', '2', '3', '4.1'], dtype='<U32')
dtype('<U32')
array([1. , 2. , 3. , 4.1])
dtype('float64')
array([1, 2, 3, 4])
dtype('int64')
array([1.1, 2. , 3. , 4. ])
dtype('float64')
```
## [Error] string 'a'와 float을 int로 바꾸기는 불가능함
```python
ar5=np.array([1.1,'a',3,4], dtype=int)  # string 'a'와 float을 int로 바꾸기는 불가능
ar5
ar5.dtype
```
### 결과
```
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
Cell In[25], line 1
----> 1 ar5=np.array([1.1,'a',3,4], dtype=int)  # string 'a'와 float을 int로 바꾸기는 불가능
      2 ar5
      3 ar5.dtype

ValueError: invalid literal for int() with base 10: 'a'
```
## matrix (2차원)
```python
m1=np.array([[1,2,5,8],[1,2,5,8],[1,2,5,8]])
m1
m1.dtype
m1.shape  #(행,열)
m1.ndim
m1.size
```
### 결과
```
array([[[1, 2, 5, 8],
        [1, 2, 5, 8],
        [1, 2, 5, 8]],

       [[1, 2, 5, 8],
        [1, 2, 5, 8],
        [1, 2, 5, 8]]])
dtype('int64')
(2, 3, 4)
3
24
```
## l1을 활용하여 아래 결과와 같이 2차원 matrix 만들기 1
```python
l1=['1',2,'3.1']

ar1=np.array([l1,l1],float)
ar1
ar1.dtype
ar1.shape
```
### 결과
```
array([[1. , 2. , 3.1],
       [1. , 2. , 3.1]])
dtype('float64')
(2, 3)
```
## l1을 활용하여 아래 결과와 같이 2차원 matrix 만들기 2
```python
l1=['1',2,'3.1']
l1=[int(float(x)) for x in l1]

ar1 = np.array([l1,l1],int)

ar1
ar1.dtype
ar1.shape
```
### 결과
```
array([[1, 2, 3],
       [1, 2, 3]])
dtype('int64')
(2, 3)
```
## reshape
``` python
'##########'
ar1=np.array([[1,2,3,4],[5,6,7,8]])
ar1
ar1.shape
ar1.size

'##########'
ar2=ar1.reshape(8)  #array의 shape의 크기를 변경 (size는 동일)
ar2
ar2.ndim
ar2.shape
ar2.size

'##########'
ar2=ar1.reshape(8,)
ar2
ar2.ndim
ar2.shape
ar2.size

'##########'
ar3=ar2.reshape(4,2)
ar3
ar3.ndim
ar3.shape
ar3.size
```
### 결과
```
'##########'
array([[1, 2, 3, 4],
       [5, 6, 7, 8]])
(2, 4)
8
'##########'
array([1, 2, 3, 4, 5, 6, 7, 8])
1
(8,)
8
'##########'
array([1, 2, 3, 4, 5, 6, 7, 8])
1
(8,)
8
'##########'
array([[1, 2],
       [3, 4],
       [5, 6],
       [7, 8]])
2
(4, 2)
8
```
## -1의 사용
```python
m1=[[1,2,3,4],[5,6,7,8]]

ar1=np.array([m1,m1])
ar1
ar1.shape

ar2=ar1.reshape(2,4,-1)  #전체 size 가 2로 나누어 떨어져야함 
ar2
ar2.shape
```
### 결과
```
array([[[1, 2, 3, 4],
        [5, 6, 7, 8]],

       [[1, 2, 3, 4],
        [5, 6, 7, 8]]])
(2, 2, 4)
array([[[1, 2],
        [3, 4],
        [5, 6],
        [7, 8]],

       [[1, 2],
        [3, 4],
        [5, 6],
        [7, 8]]])
(2, 4, 2)
```
## vector(n) vs matrix(1,n)
```python
m1=[[1,2,3,4],[5,6,7,8]]
ar1=np.array(m1)

ar2=ar1.reshape(8,)  # 8개의 요소를 가진 1차원 배열
ar2
ar2.shape

ar3=ar1.reshape(1,8)  # 8개의 요소를 가지지만 2차원 배열의 형태 (대괄호 두 개)
ar3
ar3.shape

'#########참고: -1의 이용###########'

ar2=ar1.reshape(-1)
ar2
ar2.shape

ar3=ar1.reshape(1,-1)
ar3
ar3.shape
```
### 결과
```
array([1, 2, 3, 4, 5, 6, 7, 8])
(8,)
array([[1, 2, 3, 4, 5, 6, 7, 8]])
(1, 8)
'#########참고: -1의 이용###########'
array([1, 2, 3, 4, 5, 6, 7, 8])
(8,)
array([[1, 2, 3, 4, 5, 6, 7, 8]])
(1, 8)
```
## flatten()
```python
m1=[[1,2,3,4],[5,6,7,8]]
ar1=np.array(m1)

ar1.reshape(-1,) #1차원 array로 변환
ar1.flatten()  #1차원 array로 변환


'#######################'

m1=[[1,2,3,4],[5,6,7,8]]
ar2=np.array([m1,m1])
ar2.flatten()
```
### 결과
```
array([1, 2, 3, 4, 5, 6, 7, 8])
array([1, 2, 3, 4, 5, 6, 7, 8])
'#######################'
array([1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8])
```
## 주어진 v1을 가지고 가능한 모든 2차원 matrix를 만들기
```python
ar1=np.array([1,2,3,4,5,6,7,8,9,10,11,12])
'## 주어진 v1'
ar1

'## 가능한 2차원 matrix'
ar2=ar1.reshape(1,-1) #모
ar2
ar3=ar1.reshape(2,-1) #두
ar3
ar4=ar1.reshape(3,-1) #나
ar4
ar5=ar1.reshape(4,-1) #누
ar5
ar6=ar1.reshape(6,-1) #어 떨어
ar6
ar7=ar1.reshape(12,-1) #짐
ar7
```
### 결과
```
'## 주어진 v1'
array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12])
'## 가능한 2차원 matrix'
array([[ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12]])
array([[ 1,  2,  3,  4,  5,  6],
       [ 7,  8,  9, 10, 11, 12]])
array([[ 1,  2,  3,  4],
       [ 5,  6,  7,  8],
       [ 9, 10, 11, 12]])
array([[ 1,  2,  3],
       [ 4,  5,  6],
       [ 7,  8,  9],
       [10, 11, 12]])
array([[ 1,  2],
       [ 3,  4],
       [ 5,  6],
       [ 7,  8],
       [ 9, 10],
       [11, 12]])
array([[ 1],
       [ 2],
       [ 3],
       [ 4],
       [ 5],
       [ 6],
       [ 7],
       [ 8],
       [ 9],
       [10],
       [11],
       [12]])
```
## arange / array + range   
default 시작은 0부터, step은 1, 끝은 포함되지 않음 
```python
## array + range
ar1=np.array(range(0,12)).reshape(3,4)
ar1
ar2=np.array(range(4,12)).reshape(2,4)
ar2
ar2=np.array(range(0,100,4)).reshape(5,5)
ar2
```
### 결과
```
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
array([[ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
array([[ 0,  4,  8, 12, 16],
       [20, 24, 28, 32, 36],
       [40, 44, 48, 52, 56],
       [60, 64, 68, 72, 76],
       [80, 84, 88, 92, 96]])
```
## 3차원 tensor 실습   
```python
print('# 1)')
ar1= np.arange(1,61).reshape(5,3,4)  #삼차원 tensor
ar1

print('# 2)')
ar2=np.arange(1,61).reshape(-1)  #1차원 vector
ar2

print('# 3)')
ar3= np.arange(1,61).reshape(-1,10)  # 10으로 나누어 떨어짐 
ar3

print('# 4)')
ar4=np.arange(3,6,0.4).reshape(2,4)  
ar4
```
### 결과
```
# 1)
array([[[ 1,  2,  3,  4],
        [ 5,  6,  7,  8],
        [ 9, 10, 11, 12]],

       [[13, 14, 15, 16],
        [17, 18, 19, 20],
        [21, 22, 23, 24]],

       [[25, 26, 27, 28],
        [29, 30, 31, 32],
        [33, 34, 35, 36]],

       [[37, 38, 39, 40],
        [41, 42, 43, 44],
        [45, 46, 47, 48]],

       [[49, 50, 51, 52],
        [53, 54, 55, 56],
        [57, 58, 59, 60]]])
# 2)
array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
       18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34,
       35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51,
       52, 53, 54, 55, 56, 57, 58, 59, 60])
# 3)
array([[ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10],
       [11, 12, 13, 14, 15, 16, 17, 18, 19, 20],
       [21, 22, 23, 24, 25, 26, 27, 28, 29, 30],
       [31, 32, 33, 34, 35, 36, 37, 38, 39, 40],
       [41, 42, 43, 44, 45, 46, 47, 48, 49, 50],
       [51, 52, 53, 54, 55, 56, 57, 58, 59, 60]])
# 4)
array([[3. , 3.4, 3.8, 4.2],
       [4.6, 5. , 5.4, 5.8]])
```
