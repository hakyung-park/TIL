# JavaScript



- 다른 언어에 비해 flexible하기 때문에 공부하기 쉽지 않다.
  - 파이썬처럼 객체지향 + 함수적 특성이 혼합되어 있음
- 과거에는 웹 페이지 내부에서 동작하는 프로그래밍 언어였다.
- browser 기반으로 실행한다.
- 현재는 `Node.js` 등은 웹 browser가 아닌 OS상에서도 실행이 가능하다.
- 나는 HTML과 CSS를 동적으로 handling하는 목적으로 사용할 것임.
  - __HTML 의 <head>에서 link시켜서 사용__
- 프로그래밍 언어로, data type, control statement를 가지고 있음.
- 위에서부터 순차적으로 실행이 된다.



### 예시

```html
<!-- .html 파일 -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
	<script scr="js/myScript.js"></script> 
  
</head>
<body>
    <h1>여기는 첫번째 H1</h1>
	<script>
        // 여기에 javascript code
	</script>
	<h1>여기는 두번째 H1</h1>
</body>
</html>
```

```javascript
// .js 파일

alert("alert창이 뜹니다!") // blocking 함수 (확인버튼 누르면 다음으로 넘어감)
```



### 문법

- __변수__ 만드는 방법에 여러가지가 있다.

  - `let a = 100;` 
  - python처럼 `a = 100`처럼 만들 수 있다. 
    - 전역변수처럼 사용되며 let과 다르다.
  - `var`는 과거에 쓰던 문법이다.
    
    ``` javascript
    let a = 100;         // number 숫자형
    let b = 'Hello';     // string 문자열
    let c = true;        // boolean
    let d = [1, 2, 3]    // array 배열
    let e = {            // literal 객체 object
        name: '홍길동',
        age: 25,
        address: '서울'
    }
    ```
    
  
- __객체__를 사용하는 법은 두가지가 있다.

  - associated array 배열 형태로
  - dot operator 객체의 특성을 활용

  ```javascript
  e.address               // 객체이므로 dot operator을 사용할 수 있다
  console.log(e.address)  // console.log에 찍음 ---> 개발자 도구 > Console에서 확인 가능
  console.log(e['age'])   // 주의! 문자열 형태로 키값을 주어야 함
  ```

- __함수__

  - 선언적 함수

  ```javascript
  /* Python에서
  
  def my_func(x,y):
  	result = x + y		
  	return result
  */
  
  // JavaScript에서는
  function my_func(x,y) {
      let result = x + y;
      return result;
  }
  ```

  - 일급함수(First-classes function)을 지원
    - 함수가 변수에 저장될 수 있다.
    - 결과 값으로 함수를 리턴할 수 있다.
    - 다른 함수의 인자로 함수를 이용할 수 있다.

  ```javascript
  let tmp6 = function {      // my_func라는 이름을 굳이 설정할 필요가 없기때문에 쓰지 않는다.
      let result = x + y;
      return result;
  }
  ```

  

