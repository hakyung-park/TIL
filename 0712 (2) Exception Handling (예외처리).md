# Exception Handling (예외처리)



- 일반적으로 programming 언어에서 Error, Exception
  - `Error`: 복구가 불가능한 예외적인 상황 $\rightarrow$ 프로그램의 실행이 중단
  - `Exception`: 복구가 가능한 오류 상태 $\rightarrow$ 프로그램의 실행이 중단되지 않고 지속적인 수행이 가능(처리 후)

```python
a = 100 / 0   # 무한대임 ---> 컴퓨터가 이해하지 못함

print(a)   # ZeroDivisionError 오류가 발생하며 프로그램이 종료됨
```

<img src="C:\Typora image\image-20210712201455253.png" alt="image-20210712201455253" style="zoom: 50%;" />

- `try ` 와 `except`구문을 통해 예외 처리를 할 수 있다.

```python
try: 
    a = 100/0
    
except ZeroDivisionError: 
	# 오류를 고치는 code ... 
    print('0으로 나눌 수 없어요!')   # ---> 만약 zerodivision error가 나온다면 해당문구를 print하고 강제종료하지 말아라
    
print('Hello world')
```

<img src="C:\Typora image\image-20210712201752436.png" alt="image-20210712201752436" style="zoom:67%;" />



```python
try: 
    my_list = [1,2]
    my_sum = my_list[0] + my_list[1] + my_list[2]   # out of range 오류가 날 것
   
except ZeroDivisionError:   # 이 것만 있다면, 상관없는 오류명으로 프로그램이 종료됨
    print('0으로 나눌 수 없어요!')
except IndexError: 
    print('index 사용에 문제가 있어요!')
    
print('Hello World')
```

<img src="C:\Users\oenom\AppData\Roaming\Typora\typora-user-images\image-20210712205049575.png" alt="image-20210712205049575" style="zoom:67%;" />



- `except` : 위 오류에 해당되지 않지만 오류일 때 수행이 되는 부분
- `finally` : 오류와 상관없이 무조건 실행되는 부분

```python
try:
	my_list = ['1', '2']
	my_sum = 100 + my_list[0]
	
except ZeroDivisionError:
    print('0으로 나눌 수 없어요!')
except IndexError: 
    print('index 사용에 문제가 있어요!')
except:
	print('예기치 않은 문제가 있어요!')
finally:
    print('오류의 여부와 상관없이 무조건 실행')
	
print('Hello World')
```



- __Q )__ 오류가 생길만한 코드에 임의로 `try`구문을 이용해서 예외처리를 하면 될까?
  - __A )__ 일반적으로 `try`구문이 강제되는 코드들이 있다.

