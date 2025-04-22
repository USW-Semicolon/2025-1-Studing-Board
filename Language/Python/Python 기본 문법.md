# 파이썬 기본 문법

---

## 📌 1. 변수

- **객체**를 가리키는 것
- `=` 기호를 사용

```python
a = 1
b = "python"
c = [1, 2, 3]
```

 ✔️ a, b, c → **변수**

---

## 📌 2. 숫자형

- **숫자** 형태로 이루어진 자료형
- 정수형: `int`
- 실수형: `float`

```python
a = 5           # 정수형
b = 2           # 정수형
c = 1.2         # 실수형

print(a + b)    # 더하기: 7
print(a - b)    # 빼기: 3
print(a * b)    # 곱하기: 10
print(a ** b)   # 거듭제곱: 25
print(a / b)    # 나누기: 2.5
print(a // b)   # 몫: 2
print(a % b)    # 나머지: 1
```

**문제 011**

*삼성전자라는 변수로 50,000원을 바인딩*

*주식 10주를 보유하고 있을 때 총 평가금액은?*

```python
삼성전자 = 50000
총 평가금액 = 삼성전자 * 10
print(총 평가금액)           # 500000
```

---

## 📌 3. 문자열 자료형

- **문자, 단어** 등으로 구성된 문자들의 집합
- `" "` 또는 `' '`로 둘러싸여 있으면 모두 문자열
- ex: `"123"` , `'python'`

```python
# 문자열 더하기
a = "app"
b = "le"
print(a + b)      # apple

# 문자열 곱하기
a = "apple"
print(a * 2)      #appleapple
```

- 파이썬은 0부터 숫자를 셈

```python
# 문자열 인덱싱
a = "python study"
print(a[2])        # t
print(a[5])        # n
print(a[-2])       # d

# 문자열 슬라이싱
a = "python study"
print(a[0:6])      # python
print(a[7:12])     # study
```

**⭐문자열 관련 함수들**

```python
# 문자 개수 세기
a = "apple"
print(a.count('p'))                    # 2

# 위치 알려주기
a = "python"
print(a.find('y'))                     # 1
print(a.index('y'))                    # 1

# 소문자 → 대문자
a = "abcd"
print(a.upper())                       # ABCD

# 대문자 → 소문자
a = "ABCD"
print(a.lower())                       # abcd

# 문자열 바꾸기
a = "python study"
print(a.replace("python", "game"))     # game study
```

**문제 022**

*자동차 번호가 다음과 같을 때 뒤에 4자리만 출력 (156다 9119)*

```python
number plate= "156다 9119"
print(number plate[-4:])      # 9119
```

**문제 041**

다음과 같은 문자열이 있을 때 이를 대문자 BTC_KRW로 변경

```python
ticker = "btc_krw"
print(ticker.upper())        # BTC_KRW
```

---

## 📌 4. 리스트 자료형

- `[ ]` 로 감싸 주고 각 요솟값은 `,` 로 구분
- **수정 가능**

```python
# 리스트 더하기
a = [1, 2, 3]
b = [4, 5, 6]
print(a + b)     # [1, 2, 3, 4, 5, 6]

# 리스트 반복하기
a = [1, 2, 3]
print(a * 3)     # [1, 2, 3, 1, 2, 3, 1, 2, 3]
```

```python
# 리스트 수정
a = [1, 2, 3]
a[2] = 4          # 3 → 4
print(a)          # [1, 2, 4]

# 리스트 삭제
a = [1, 2, 3]
del a[1]
print(a)          # [1, 3]
```

⭐**리스트 관련 함수들**

```python
# 리스트 추가
a = [1, 2, 3]
a.append(4)       # 맨 마지막에 추가
print(a)          # [1, 2, 3, 4]

# 리스트 정렬
a = [1, 4, 3, 2]
a.sort()          # 순서대로
print(a)          # [1, 2, 3, 4]

# 리스트 뒤집기
a = ['a', 'b', 'c']
a.reverse()
print(a)          # ['c', 'b', 'a']

# 리스트 삽입
a = [1, 3, 4]
a.insert(1, 2)
print(a)          # [1, 2, 3, 4]

# 리스트 제거
a = [1, 2, 3]
a.remove(1)
print(a)          # [2, 3]

# 리스트 끄집어내기
a = [1, 2, 3]
print(a.pop())    # 3 → 맨 마지막 요소
print(a)          # [1, 2] → 맨 마지막 요소를 끄집어 낸 결과
```

**문제 051, 052**

*영화 예매 순위 top3가 다음과 같을 때 (닥터 스트레인지, 스플릿, 럭키)*

*영화 제목을 movie_rank 이름의 리스트에 저장 후 "배트맨"을 추가*

```python
movie_rank = ["닥터 스트레인지", "스플릿", "럭키"]
movie_rank.append("베트맨")
print(movie_rank)           # ['닥터 스트레인지', '스플릿', '럭키', '베트맨']
```

**문제 070**

*리스트에 있는 값을 오름차순으로 정렬*

```python
data = [2, 4, 3, 1, 5, 10, 9]
data.sort()
print(data)           # [1, 2, 3, 4, 5, 9, 10]
```

---

## 📌 5. 튜플 자료형

- `( )` 으로 둘러싸임
- 1개의 요소만을 가질 때 요소 뒤에 `,`  반드시 붙임 → `a = (1, )`
- **수정 불가능**

```python
# 튜플 길이 구하기
a = (1, 2, 3, 4)
print(len(a))       # 4
```

**문제 073**

*숫자 1 이 저장된 튜플을 생성*

```python
my_tuple = (1, )
```

**문제 076**

*변수 t는 t = ('a', 'b', 'c')와 같은 값이 저장*

*변수 t가 ('A', 'b', 'c') 튜플을 가리키도록 수정*

```python
t = ('A', 'b', 'c')   # 튜플은 수정 불가능
```

---

## 📌 6. 딕셔너리 자료형

- **Key와 Value**를 한 쌍으로 가지는 자료형
- `{ }` 를 사용

```python
# 딕셔너리 쌍 추가
a = {1: 'a'}
a[2] = 'b'      # {2: 'b'} 쌍 추가
print(a)        # {1: 'a', 2: 'b'}

# 딕셔너리 요소 삭제
a = {1: 'a', 2: 'b'}
del a[1]
print(a)        # {2: 'b'}
```

⭐딕셔너리 관련 함수들

```python
# key 리스트 만들기
a = {"name": "hoyeon", "phone": "010-2289-2123", "birth": "1223"}
print(a.keys())       # dict_keys(['name', 'phone', 'birth'])

# value 리스트 만들기
a = {"name": "hoyeon", "phone": "010-2289-2123", "birth": "1223"}
print(a.values())     # dict_values(['hoyeon', '010-2289-2123', '1223'])

# key, value 쌍 얻기
a = {"name": "hoyeon", "phone": "010-2289-2123", "birth": "1223"}
print(a.items()
  # dict_items([('name', 'hoyeon'), ('phone', '010-2289-2123'), ('birth', '1223')])
  
# key로 value 얻기
a = {"name": "hoyeon", "phone": "010-2289-2123", "birth": "1223"}
print(a.get("name"))  # hoyeon
```

**문제 085**

*아이스크림의 이름과 가격을 딕셔너리로 구성*

*→메로나(1000), 폴라포(1200), 빵빠레(1800)*

```python
ice = {'메로나': 1000, '폴라포': 1200, '빵빠레': 1800}
print(ice)              # {'메로나': 1000, '폴라포': 1200, '빵빠레': 1800}
```

**문제 095**

*다음의 딕셔너리로부터 key 값으로만 구성된 리스트를 생성*

```python
icecream = {'탱크보이': 1200, '폴라포': 1200, '빵빠레': 1800, '월드콘': 1500, '메로나': 1000}
print(icecream.keys())
    # dict_keys(['탱크보이', '폴라포', '빵빠레', '월드콘', '메로나'])
```

---

## 📌 7. 집합 자료형

- **중복 허용X**
- **순서X**

```python
# 예시
a = set("hello")
print(a)       # {'l', 'e', 'h', 'o'}
```

```python
# 교집합 구하기
a = set([1, 2, 3])
b = set([3, 4, 5])
print(a & b)      # {3}

# 합집합 구하기
a = set([1, 2, 3])
b = set([3, 4, 5])
print(a | b)      # {1, 2, 3, 4, 5}

# 차집합 구하기
a = set([1, 2, 3])
b = set([3, 4, 5])
print(a - b)      # {1, 2}
print(b - a)      # {4, 5}
```

---

## 📌 8. 불 자료형

- `True` : 참, `False` : 거짓

```python
if [1, 2, 3]:
     print("참")
else:
     print("거짓")       # 참

# 불 연산   
print(bool('python'))    # True
print(bool(''))          # False

```

**문제 104**

*다음 문제의 결과를 예상*
```python
x = 4
print(1 < x < 5)    # True
```

---