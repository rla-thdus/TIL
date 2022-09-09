# Error vs Exception
프로그램이 실행 중 어떤 원인에 의해서 오작동을 하거나 비정상적으로 종료되는 경우를 프로그램 오류라고 한다.<br>
프로그램 오류는 `Error` 와 `Exception` 으로 구분할 수 있다.

## Error
컴파일 시 문법적인 오류와 런타임 시 널포인트 참조와 같은 오류로 프로세스에 심각한 문제를 발생 시켜 프로세스를 종료 시킬 수 있다.<br>
즉, 메모리 부족이나 스택오버플로우와 같이 발생하면 복구할 수 없는 심각한 오류이다.

## Exception
문장이나 표현식이 문법적으로 올바르다 할지라도, 에러를 일으키고 싶다면 일으킬 수 있다.<br>
실행 중에 감지되는 오류들을 예외 라고 부르는데 예외는 무조건 치명적이지 않다.

즉, 발생하더라도 수습할 수 있는 비교적 덜 심각한 오류이다.<br>
에러의 상황을 예방하기 위해 예외 상황을 만들 수 있는데 이는 파이썬에서 try-exception 으로 예외 처리를 할 수 있다.

# try-except
### 사용 예시
else와 finally는 사용하고 싶으면 적어주면 된다.<br>
필요하지 않을 때는 그냥 try와 except로만 예외 처리를 할 수 있다.

```python
try:
    예외가 발생할 수 있는 코드
except:
    예외가 발생했을때 실행할 코드
else:
    예외가 발생하지 않았을 때 실행할 코드
finally:
    예외 발생했는지와 상관없이 무조건 실행할 코드
```

### e.g. 나눗셈을 하는 함수 안에서의 예외 처리
```python
def division(a, b):
    try:
        result = a / b
    except ZeroDivisionError as e:
        print(e)
    else:
        print(f'나눗셈 계산 결과는 {result} 입니다.')
    finally:
        print('--종료--')
    return result
```

## raise
직접 예외를 발생시킬 수 있다.

```python
def division():
    a, b = map(int, input().split())
    if(b == 0):
        raise ZeroDivisionError('0으로 나눌 순 없습니다.')
    return a/b

try:
    division()
except ZeroDivisionError as e:
    print(e)
```

---

[^1] https://docs.python.org/ko/3/tutorial/errors.html<br>
[^2] https://stackoverflow.com/questions/60708789/exceptions-vs-errors-in-python
