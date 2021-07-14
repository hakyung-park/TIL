# jQuery



- JavaScript는 wep page를 동적으로 handling 하기 위한 web 언어

  - 함수형 언어 + 객체지향 언어의 특성을 다 가지고 있어서 언어 자체가 약간 어려운 편에 속한다. 
  - 실행되는 환경이 browser환경으로, JavaScript Engine은 browser 안에 포함되어 있다.
  - 따라서 환경마다(Chrome, IE, ...) 설정이 다르기 때문에 fragmentation(파편화)현상이 발생한다. 
  - 현재는 TypeScript라는 언어가 표준으로 만들어져 발전하고 있다.
  - 이러한 문제 때문에 순수한 JavaScript 언어를 사용하는 것보다 다른 방법을 이용해서 browser의 동적처리를 하려고 시도했다.
  - 그래서 library가 많이 만들어졌고, 그 중 가장 성공적인 게 `jQuery`이다!

- jQury 장점

  - Cross platform(browser)를 지원하는 특징을 가지고 있다.
  - open source다. 
  - 쉽고 빠르게 배울 수 있다.
  - 화면 제어를 쉽게 할 수 있다.
  - AJAX 구현을 쉽게 할 수 있다.

- __설정__

  - CDN(Contents Delivery Network) 방식으로 사용하면 편리하다. (링크)

  - 다음과 같은 코드를 <head>에 넣어준다.

    ```html
    <script src="https://code.jquery.com/jquery-2.2.4.min.js" integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44=" crossorigin="anonymous"></script>
    ```

  - jQuery CDN을 최상단에 놓는 게 좋다. 순차적으로 설정이 되기 때문!

  - Setting > Libraries에서 사용하는 라이브러리를 확인/다운로드 할 수 있다.

  <img src="../../../AppData/Roaming/Typora/typora-user-images/image-20210714103856509.png" alt="image-20210714103856509" style="zoom:67%;" />

  <img src="../../../AppData/Roaming/Typora/typora-user-images/image-20210714103922905.png" alt="image-20210714103922905" style="zoom:67%;" />



### 작성

1. 내가 제어하길 원하는 element를 선택하고,

2. 선택한 element에 대해 method를 호출한다.

- __포맷__

  - `$`로 시작한다.
  - `$("selector라고 불리는 특수한 형태의 문자열")` 

  ```javascript
  $("h1")     // 태그명을 직접적으로 명시할 수 있다.
              // h1 element를 찾아 JavaScript 영역으로 가져온다 (document object: 문서객체)
              // 이렇게 가져온 문서객체를 jQuery객체로 다시한 번 만든다.
  ```

  - 객체는 method나 property를 가지고 있다고 생각하자. 
    - 이 중 jQuery는 method만 다룬다!

  ```javascript
  $("h1").remove()
  ```



### Selector



