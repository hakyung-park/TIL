# Module 설치하기



1. 어떤 모듈을 사용할지 결정
   - `pymysl` 설치해야지!
2. 해당 module을 다운로드해서 설치해야 한다.
   - `pip`라는 module을 이용할 수 있다.
   - anaconada 환경이라면 아나콘다 기능을 이용해서 module을 다운로드, 설치한다.
     - 만약, anaconda 명령으로 module이 설치가 안된다면 pip로 설치한다.
3. pymysql 설치
   - `Anaconda Prompt` 로 설치하는 경우
     - (가상환경으로 접속) `conda activate data_env`
     - `conda install pymysql` 입력
   - `Jupyter Notebook` 로 설치하는 경우
     - `$pip install pymysql`
   - `Google Colab` 로 설치하는 경우
     - 대부분의 module이 이미 설치되어 있을 것!
     - 안되어있다면, `pip insatll pymysql` 



---

# Python에서 설치한 module 사용하기



```python
# 필요한 module import 
import pymysql

# 데이터베이스 connection이 필요
# 내가 사용하려는 database에 대한 논리적인 연결 객체가 필요
# 접송에 대한 정보를 인자로 넘겨줘야 한다.
conn = pymysql.connect(host='localhost', 
                       db='library', 
                       user='python'
                       password='python'
                       charset='utf8')   # 한글사용으로 유니코드

# 접속이 성공하면 instance가 생성되고, 그렇지 않으면 None이 들어온다.
print(conn)

# 이제 해당 instance를 이용해서 Query를 실행할 수 있다.
# 사용하려는 cursors 객체를 생성한다.
cursor = conn.cursors() 

# 이렇게 만들면 나중에 결과데이터가 tuple에 중첩된 형태로 나온다.
# 보기 힘들기 때문에 결과값을 dict 형태로 만들기 위해 아래와 같이 설정하는 게 좋다.
cursor = conn.cursor(pymysql.cursors.DictCursor)

# SQL 구문을 만들어야 한다.
sql = 'SELECT btitle, bauthor, bprice FROM book WHERE bprice > 50000;'

# 생성한 SQL 문장을 cursor를 통해서 실행시킨다.
cursor.execute(sql)

# fetch계열의 함수를 이용해서 결과를 cursor로부터 가져온다.
result = cursor.fetchall()
print(result)   # 결과가 dict, list 형태로 나오게 된다.

```

<img src="C:\Typora image\image-20210712101610273.png" alt="image-20210712101610273" style="zoom:67%;" />



```python
for bookDict in result:
    print('제목 : {}, 저자 : {}'.format(bookDict['btitle'], bookDict['bauthor']))
```

<img src="C:\Typora image\image-20210712101754815.png" alt="image-20210712101754815" style="zoom:67%;" />



```python
# 키워드를 입력받아서 해당 키워드를 책 제목에 포함하는 책을 검색한 후 
# 책의 제목과 저자를 출력하자
import pymysql 

conn = pymysql.connect(host='localhost', 
                       db='library', 
                       user='python'
                       password='python'
                       charset='utf8') 
cursor = conn.cursor(pymysql.cursors.DictCursor)

search_keyword = input('검색키워드 : ')

sql = 'SELECT btitle, bauthor, bprice FROM book WHERE btitle LIKE '%{}%''.format(serch_keyword)

print(sql)
```

<img src="C:\Typora image\image-20210712104158553.png" alt="image-20210712104158553" style="zoom:67%;" />



```python
cursor.execute(sql)

result = cursor.fetchall()

for bookDict in result:
    print('제목 : {}, 저자 : {}'.format(bookDict['btitle'], bookDict['bauthor']))
```

<img src="C:\Typora image\image-20210712104338116.png" alt="image-20210712104338116" style="zoom:67%;" />



