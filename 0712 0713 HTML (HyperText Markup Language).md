# HTML (HyperText Markup Language)

- `태그` 언어라고 불리는 프로그래밍 언어이다.

- 로직, 데이터 타입이라는 개념은 없고, 화면에 뿌려지는 것에 대한 언어이다.

- 우리가 HTML을 이용하여 파일을 만들면 그 파일을 Web Browser(Chrome)가 불러들여서 Rendering하면 우리가 보는 Web Page가 나온다.

  

### 태그

##### `<html> ... </html>` 안에 쓰면 된다.

- `<html lang=ko>` 에서 html은 tag명, lang은 attribute(속성)

- 하나의 태그에 여러 속성이 붙을 수 있다.

  

##### `<head> ... </head>` : 환경설정

- `<meta charset="UTF-8"> ` : 문서에 대한 encoding을 설정 

- `<title> ... </title>` : chrome의 탭에 나오는 페이지 이름

- `<link rel="stylesheet" href="css/default.css">` : CSS 파일 연동 (css폴더에 있는 default css파일)

  

##### `<body> ... </body>` : 실제 browser가 rendering하는 내용

- `<a href='http://www.naver.com'>` 
  - `href` 속성에 있는 resource에 request를 보내는 역할을 하는 element
  - 기본적으로, URL 형식은 `protocol://ip_address:port` 이다.
    - `protocol`: 통신규약(데이터를 주고 받기 위해서 필요한 약속)으로 '언어'의 역할(`http`: web protocol)
    - `ip_address` : 인터넷에 연결된 컴퓨터에 부여된 논리적인 주소
      - ipv4를 이용하면 `.`을 이용해서 4자리의 숫자로 표현 (192.168.8.23)
      - www.naver.com(주소, URL)를 입력하면 웹 서버에서 알아서 ip로 인식한다.
    - `port`: 하나의 숫자(0~65535)다. 이 중 0~1024번까지는 예약되어 있음. 
      - 192.169.8.23 을 www.naver.com (domain name)로 대치해서 사용하는 것
- `<br>` : 한 줄 띄우기
- 사용자 입력 양식
  - `<input type="text">` : 기본 인풋
  - `<input type="date">` : 날짜 
  - `<input type="range">` : 슬라이딩 바
  - `<input type="color">`: 색(rgb)
- `<span> ... </span>`
- `<p> ... </p>` 
- `<div> ... </div>` 



### 예시 

```html
<!DOCTYPE html>
<html lang="en">
    <!-- head는 환경설정에 대한 내용을 담고 있는 부분 -->
    <head>
        <meta charset="UTF-8"> 
        <title> 연습페이지 </title>
        <link rel="stylesheet" href="css/default.css">
    </head>
    
   
    <body>
		<h1> 제목입니다 </h1>                        
        <img src='img/applecar.jpg' width='300'>
        <a href='http://www.naver.com'>네이버로 이동해요!</a> 
        <br><br>
        <span> 안녕하세요 span </span>
        <p> 새로운 문단입니다. </p>

        <!-- CSS가 등장하기 이전 스타일을 담당하던 방식은 다음과 같다.(비효율적) -->
        <div><font color="red" size="20"> 여기는 새로운 DIV 영역입니다. </font></div>

        <!-- 이제는 css를 활용하여 다음과 같이 한다. -->
        <!-- 1. class 사용 --> 
        <div class = "myStyle"> 여기는 새로운 DIV 영역입니다. </div>
        
        <!-- 2ID selector 사용 --> 
        <div id="myId"> 여기는 ID selector를 사용하는 부분입니다. </div>

    </body>
</html>
```

