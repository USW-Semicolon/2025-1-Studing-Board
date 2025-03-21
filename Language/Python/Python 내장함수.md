Python 내장 함수 정리
============
<br>
<br>

## 내장 함수

|  함수      |              의미     |   Python   |  실행결과   |
|------------|-----------------------|-------------|------------|
|len()  |문자열의 길이 |x = "hello world' <br> print(len('x'))| 11 |
|count()|문자열의 개수|x = "hello world' <br> print(x.count('o'))|2|
|find()|문자가 처음 나오는 위치|x = 'hello world' <br> print(x.find('o'))|4|
|join()    |    문자열 사이에 문자 삽입|  x = 'hello world'<br>print('-'.join(x))   |h-e-l-l-o- -w-o-r-l-d|
|  replace()  |  문자열 바꾸기  |  x = 'hello world' <br>print(x.replace(' ','-'))  |  	hello-world |
|   strip() |   전체 공백 제거 |    x = ' hello world ' <br>print(x.strip())|helloworld   |
|  abs() |   절댓값 리턴 | x=5, y=-5<br>print(abs(x),abs(y)) |   5 5|
|list()    |  반복 가능한 데이터를 입력받아<br>리스트로 만들어 리턴 | list("python")  | ['p', 'y', 't', 'h', 'o', 'n'] |
| range()   |  범위 값을 반복 가능한 <br>객체로 리턴 |list(range(5))<br> list(range(5, 10))  <br>list(range(1, 10, 2))<br>list(range(0, -10, -1))| [0, 1, 2, 3, 4]<br> [5, 6, 7, 8, 9]<br>[1, 3, 5, 7, 9]<br>[0, -1, -2, -3, -4, -5, -6, -7, -8, -9]|
|  sorted()  |  값을 정렬하여, 리스트로 변환  |  x=[10,30,50,20,40] <br> print(sorted(x)) | 	x=[10,20,30,40,50]  |
|float()    | 데이터를 실수로 변환   |  print(float(5))   |  	5.0 |
|    int() |   	데이터를 정수로 변환  | print(int(5.5))   |    	5|
|   str()  |  데이터를 문자열 형태로 변환   | x=5 <br> y=5 <br>print(str(x)+str(y)) | 55   |

<img src="C:\Users\duaul\Desktop\편집완료\4ee1f3c06a1b47031e4861b7f4ca61ce">
