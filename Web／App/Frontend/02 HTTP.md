# 💬 서버와 클라이언트 
### 클라이언트 (client) : 데이터나 서비스를 요청하는 프로그램
### 서버 (sever) : 클라이언트에 데이터나 서비스를 제공하는 프로그램   



### 서버의 종류
영상, 파일, 도메인, 이메일, 채팅, 게임, 앱등..




### 💬 프로토콜 (protocol)
* 컴퓨터나 원거리 통신 장비 사이에서 메시지를 주고 받는 양식과 규칙 체계   
* ___서버와 클라이언트가 데이터를 주고 받는 규약___


### 프로토콜의 종류
HTTP : Hyper Text Transfer Protocol   
HTTPS : Secure Hyper Text Transfer Protocol   
FTP : File Transfer Protocol (파일을 주는 서버)   
SFTP : Secure File Transfer Protocol   
Telnet : TErminaL NETwork   
POP3 : Post Office Protocol version 3   
SMTP : Simple Mail Transfer Protocol   
SSH : Secure Shell   
SSL : Secure Socket Layer   
SOAP : Simple Object Access Protocol   
ARP : Adress Resolution Protocol   

### 💬 HTTP
`HyperText Transfer Protocol`,(하이퍼본문전송규약) 은 웹에서 정보를 주고받을 수 있는 프로토콜.   

* 주로 HTML 문서를 주고받는 데에 쓰인다.   
* ___`80번 포트`를 기본으로 사용한다.___
* ___클라이언트와 서버 사이에 이루어지는 `요청/응답(request/response)` 프로토콜임.___   
* ___HTTP를 통해 전달되는 자료는 `http:로 시작하는 URL(인터넷 주소)로 조회`할 수 있다.___

### 💬 HTML (HyperText Markup Language) 
* 웹페이지를 만드는 마크업 언어   
* `구조적 문서를 만들 수 있는 방법`을 제공 - 제목, 단락, 목록, 링크, 표, 그림, 동영상, 인용 등

### HTML Request Methods
* `요청 메소드(Request Methods)`
`GET`   
읽기 기능   
`클라이언트가 서버에 데이터를 요청`   
`POST`   
쓰기 기능   
`특정 데이터를 추가 할 것을 요청`   
PUT   
수정 기능   
특정 데이터에 대해 수정하라는 요청   
DELETE   
삭제 기능   
특정 데이터를 삭제할 것을 요청   

### HTTP 프로토콜



1. 웹 브라우저(클라이언트)는 웹서버(서버)에 HTML 파일을 요청    
2. `URL을 이용`하여 서버에 받고 싶은 HTML 파일을 지정   
3. 웹서버는 요청한 HTML 파일을 전송   

### HTTP Status Code (응답코드)
* 서버가 클라이언트의 요청을 처리한 후, `클라이언트에 처리 결과를 알려주는 코드`   
1xx : 조건부 응답   
`2xx : 성공`   
3xx : 리다이렉션 완료 (다른 주소로 이동)    
4xx : 요청 오류   
5xx : 서버 오류   



### URL
예시 : "`https`://`www.google.com`/`search`?`q=python`"   
프로토콜:` https `  
호스트: `www.google.com  `    
경로: `search`   
쿼리스트링: `q=python `  
* ___쿼리스트링 ?___
* 클라이언크가 요청할 때 보내는 추가적인 데이터(변수)   
* 리소스 경로와 쿼리스트링은 `'?'로 구분`
* 쿼리스트링 안에서 '&'를 이용하여 각각의 변수를 구분   
예시 : "http://www.example.com/product?pro=1&cate=2"
`pro 값으로 1, cate 값으로 2를 할당`하여 서버에 보냄   

### 💬 Header
- 서버와 클라이언트 간에 데이터를 주고 받을 때, `헤더라는 정보를 포함해서 보낸다.`
* `요청 헤더(Request header)`
클라이언트가 서버에 요청 할 때 포함되는 헤더
* `응답 헤더(Response header)`
서버가 클라이언트의 요청에 응답 할 때 포함되는 헤더   

* 미디어의 종류, 인코딩(압축) 방법, 기본 URL, 쿠키 등 다양한 정보를 보낼 수 있다.

* chrome 브라우저에서 헤더 정보 보기
   [F12] - [Network] - [Name에 있는 엔티티 클릭]

### 💬 웹 페이지 접속   
___requests 모듈을 이용하여 웹페이지 접속하기___
    
```python
import requests as rq
url='https://www.google.com'
res=rq.get(url) # requests 모듈의 get()함수를 이용하여 요청 보내기
print(res) # 응답결과 출력
## <Response [200]>
print(res.text) # HTML 문서출력
## ...
## <html lang="ko">
## <head>
## <meta charset="utf-8">
## <meta name="Referrer" content="origin">
## ...

print(res.status_code) # 응답코드 출력
## True
```

```python
import requests as rq

res = rq.get('http://naver.com') # res: 응답객체(response object)

print(res.headers) # 응답헤더
print(res.request.headers) # 요청헤더
print(res.url) # URL
print(res.status_code) # 상태코드
print(dir(res))  # res의 모든 속성 출력 (Print all attributes of res)
```
### URL 적합성 체크하는 함수 만들기
1. url 요청이 성공 했다면, 'success', url, status code를 출력     
1. url 요청이 실패하면 'fail'과 url, status code를 출력   
```python
import requests as rq
def check_url(url):
    res = rq.get(url)  #서버에 데이터를 요청
    if res.status_code == 200: # 상태코드가 200이면 성공적 
        print(f"success: {url},{res.status_code}")
    else:
        print(f"failed: {url},{res.status_code}") # 아니면 실패
    pass


check_url('https://www.naver.com/')
check_url('https://www.naver.com/a')

## 결과
# success: https://www.naver.com/, 200
# failed: https://www.naver.com/a, 404
```

### URL의 응답 헤더 print_header() 요청
```python
import requests as rq
def print_header(url):
    res = rq.get(url)  # 서버에 데이터를 요청

    for key in res.headers:
        value = res.headers[key] 
        print(f"{key}:{value}") # 받은 응답 헤더(res.headers) 를 키-값으로 출력

print("[구글 헤더]")
print_header('https://www.google.com')
print("[다음 헤더]")
print_header('https://www.daum.net')
```

### 요청해더(request header)을 출력하는 함수 print_request_header()
```python
import requests as rq
def print_request_header(url):
    res = rq.get(url)

    for key in res.headers:
        value = res.headers[key]
        print(f"{key}:{value}")
     
    pass


print("[구글 요청헤더]")
print_request_header('https://www.google.com')
print()
print("[다음 요청헤더]")
print_request_header('https://www.daum.net')
```
