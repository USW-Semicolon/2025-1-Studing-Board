# 🐰 중심극한정리
`모집단의 분포가 무엇이든 관계없이 n이 크면 표본평균 𝑋 ̅의 분포는 근사적으로 정규분포가 된다.`
   
<img width="287" alt="스크린샷 2025-04-12 오후 11 07 14" src="https://github.com/user-attachments/assets/66acca54-ae4c-470d-9001-aadb37792ce8" />

## sample (표본)
* 총 2,000개의 표본(행) / 한 표본의 개수는 10,000개(열) 
```python
# histogram 그리는 함수 정의
import matplotlib.pyplot as plt

def draw_hist(ar1, nbin=20):
    fog, ax=plt.subplot()
    _=ax.hist(ar1, bins=nbin, edgecolor='k')
# 표본의 분포 histogram 그리기
s2= np.random.uniform(3,5,size=(2000,10000))
print('sample dist> mean: {:.4f}, std: {:,4f}' .format(s1.mean(),s1.std()))
```
<img width="274" alt="스크린샷 2025-04-12 오후 11 08 17" src="https://github.com/user-attachments/assets/d4fd232b-354b-4a7a-8d67-69a8fc9ea218" />

## 표본평균들의 분포
```python
#for loop 사용
m1=[] # 빈 리스트 생성
for i in range(2000): # 2000번 뽑기
    a1 = np.random.uniform(3,5,size=10000) # 3부터 5까지의 숫자들중 사이즈가 10000개인 표본을 랜덤으로 추출
    m1.append(a1.mean()) # 표본들의 평균을 m1 에 하나씩 넣기
m1 = np.array(m1) # 배열로 바꾸기

# numpy axis 사용
s2 = np.random.uniform(3,5, size=(2000,10000)) # 3부터 5 사이의 랜덤 수를 2000x10000 크기의 배열로 생성
s2[:5,:5]
m1 = s2.mean(axis=1) # 열에대한 평균 생성

m1[:10]
draw_hist(m1)
print('sample mean dist> mean: {:.4f}, std: {:.4f}' .format(m1.mean(),m1.std()))

# 표본의 크기가 10인 2000개의 표본들에 대해서 표본 중앙값의 분포 그리기
import numpy as np
import matplotlib.pyplot as plt

a1 = np.random.uniform(3, 5, size=(2000, 10))
medians = np.median(a1, axis=1)
print("a1 median dist > mean: {:.4f}, std: {:.4f}".format(medians.mean(), medians.std()))
```

<img width="292" alt="스크린샷 2025-04-12 오후 11 09 07" src="https://github.com/user-attachments/assets/1eda5052-412d-40f8-856f-eb8494ca7007" />

# array operation (array간 연산)   
* array간에는 기본적으로 `shape이 같을 때` 가능하고, element-wise 연산을 수행한다.
<img width="588" alt="스크린샷 2025-04-12 오후 11 09 50" src="https://github.com/user-attachments/assets/026c224c-315e-439f-90fa-18eb80dfb960" />

```python
# (4,8,12,16,20, … , 40)의 각 element의 제곱들의 합 구하기
a1 = np.random.uniform(4,41,4)
print(a1)
# numpy만 사용
sum_np =np.sum(a1**2)
print(sum_np)
# for loop 사용
a1 = 0
for i in a1 :
    sum_np += i ** 2
print(a1)
```
## broadcasting   
* shape이 다를 때 array간의 연산을 지원하는 기능 `(자동으로 shape을 맞춰 줌)`
<img width="562" alt="스크린샷 2025-04-12 오후 11 10 19" src="https://github.com/user-attachments/assets/d7495bf6-1470-41ce-9418-d8b417508eb3" />

```python
a1 = np.arange(6).reshape(2,3)
#array([[0, 1, 2],
       #[3, 4, 5]])
a1+2
#array([[2, 3, 4],
       #[5, 6, 7]])
a1*2
#array([[ 0,  2,  4],
       #[ 6,  8, 10]])
a1-2
#array([[-2, -1,  0],
       #[ 1,  2,  3]])
a1/2
#array([[0. , 0.5, 1. ],
       #[1.5, 2. , 2.5]])
```

```python
## 0,5,10,15, … ,50 을 3으로 나눈 나머지의 합을 구하시오
# numpy 사용
a1 = np.arange(0,51,5)
sum = np.sum(ar1 % 3) # 각 요소를 3으로 나눈 나머지의 합
print(sum)
# for loop 사용
s1 = 0
for i in ar1:
s1 += i % 3
print(s1)
## (3,5) matrix를 만들고, 각 행에 다음과 같은 값을 더하시오
# 0행 : 2, 1행 : 3, 2행 : 1
a1 = np.arange(15).reshape(3,5) 
row_add= np.array([2, 3, 1]).reshape(3,1)
add = a1 + row_add
# 0~10 사이의 랜덤 값을 세 개 뽑아서 각 행에 더하시오
a2 = np.random.randit(0,10,3).reshape(3,1)
add_random = a1 + a2

print(a1)
#[[ 0  1  2  3  4]
 #[ 5  6  7  8  9]
 #[10 11 12 13 14]]

print(add)
# [[ 2  3  4  5  6]
# [ 8  9 10 11 12]
# [11 12 13 14 15]]   

print(a2)
# [[4]
# [4]
# [4]]

print(add_random)
#[[ 4  5  6  7  8]
 #[ 9 10 11 12 13]
 #[14 15 16 17 18]]

```
`! 만약 col에 대해 더하면? 에러임 !`  
col_add = np.array([2,3,1]).reshape(1,3)   
_add = ar1 + col_add   
Traceback (most recent call last):   
  File "<pyshell#27>", line 1, in <module>   
    _add = ar1 + col_add   
"ValueError: operands could not be broadcast together with shapes (3,5) (1,3)"    
`-> (3,5)와 (1,3)은  shape 이 맞지 않기 때문에 broadcast가 안됨 , 맞으려면 (3,1) 이거나 (1,5) 이어야 함`

## concatenate
* 두 array를 축에 따라 연결함   
`np.concatenate((a1,a2,..),axis = 0)`

<img width="357" alt="스크린샷 2025-04-12 오후 11 11 41" src="https://github.com/user-attachments/assets/5f87b9ab-5026-4f9e-8ef8-39eabc82421e" />

```python
a1 = np.arange(3)
a1.shape
# (3,)
a2 = np.arange(4,8)
a2.shape
# (4,)
a3 = np.concatenate((a1,a2)) # a1와 a2를 (axis=0)축에 따라 연결함
a3.shape
# (7,)
a3
# array([0,1,2,4,5,6,7])

a1 = np.arange(12).reshape(4,3)
a1
# array([[ 0,  1,  2],
       # [ 3,  4,  5],
       # [ 6,  7,  8],
       #[ 9, 10, 11]])
a2 = np.arange(8).reshape(4,2)
a2
# array([[0, 1],
       # [2, 3],
       # [4, 5],
       # [6, 7]])

a3 = np.concatenate((a1,a2),axis=1)
a3
# array([[ 0,  1,  2,  0,  1],
       #[ 3,  4,  5,  2,  3],
       #[ 6,  7,  8,  4,  5],
       #[ 9, 10, 11,  6,  7]])
a3.shape
# (4,5) 
# axis = 1 에 대하여 a1과 a2를 연결
# dimension(차원)이 같아야함
# concatenate를 실행하지 않는 axis의 size는 같아야함

## 아래 vector에 reshape과 concatenate만을 적용하여 matrix를 만드시오
v1 = np.array([1,2,3]).reshape(1,3)
v1
# array([[1, 2, 3]])
v2 = np.concatenate([v1]*3, axis=0)
v2
# array([[1, 2, 3],
       # [1, 2, 3],
       # [1, 2, 3]])
v3 = np.array([1,2,3]).reshape(3,1)
v3
# array([[1],
       # [2],
       # [3]])
v4 = np.concatenate((v1,v2),axis=1) # 열에 대해 연결
v4
# array([[1, 2, 3, 1],
       # [1, 2, 3, 2],
       # [1, 2, 3, 3]])
```
