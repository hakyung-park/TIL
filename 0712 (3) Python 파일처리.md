# Python의 파일처리



- 실제로 python은 순수 파일처리 기능은 사용하지 않는다.

  - 왜? 너무 느리다. 따라서 대용량을 처리하기에 적합하지 않다.

- python 모듈 중 `pandas` 모듈을 이용하여 file 처리를 한다.

- __(예제)__

  - `python_ML` 폴더에 `my_student.txt` 파일을 다음과 같이 생성

    <img src="C:\Users\oenom\AppData\Roaming\Typora\typora-user-images\image-20210712210729595.png" alt="image-20210712210729595" style="zoom:67%;" />

  ```python
  file1 = open('my_student.txt', 'r')   # r: 읽기모드, w: 쓰기모드
  
  while True:
      line = file1.readline()   # 한 줄씩 읽어온다
      print(line)
  	if not line:   # line에 data가 없으면 실행
          break      # 가장 가까운 loop인 while을 빠져나간다
          
  file1.close()
  ```

  

