# Decorator란
> ### 기존 함수를 수정하지 않은 상태에서 실행 전과 후에 추가적인 동작을 할 수 있게 해준다.
> `@staticmethod`, `@classmethod` 등과 같이 앞에 `@` 로 시작하는 것들이 데코레이터다.<br>
> 쉽게 말해서 함수를 장식하는 역할이다.

### 언제 데코레이터를 사용할까
- 디버깅을 하거나, 함수 실행에 걸린 시간을 측정하고 싶을 때, 혹은 함수 실행 전 해줘야 하는 작업이 있거나 실행이 끝나고 나서 해줘야 하는 작업이 있을 경우에 사용하는 것 같다.

## 만드는 방법
### 함수 데코레이터
1. 데코레이터 함수를 만들고 호출할 함수를 파라미터로 받는다.
2. 1번에서 만든 데코레이터 함수 안에서, 호출할 함수를 감싸는 `wrapper` 함수를 만든다.
3. `wrapper` 함수 안에서 파라미터로 받은 함수를 호출한다.
4. 1번에서 만든 데코레이터 함수 안에서 정의한 `wrapper` 함수를 리턴한다.
    - 리턴할 때는 `()` 를 붙이지 않는다.

#### 기본 구조
```python
def decorator(func):
    def wrapper():
        func()
    return wrapper

@decorator
def print_hello():
    print('hello')
```

### 클래스 데코레이터
1. `__init__`, `__call__` 메서드를 적절히 오버라이드 시켜줘야 한다.
2. `__init__` 에서 호출할 함수를 파라미터로 지정한다.
3. `__call__` 에서 호출할 함수를 실행시켜준다.

#### 기본 구조
```python
class Decorator:
    def __init__(self, func):
        self.func = func

    def __call__(self):
        self.func()

@Decorator
def print_hello():
    print('hello')
```

## 호출 방법
### 1. `@` 구문 사용해서 호출하기.
```python
def decorator(func):
    def wrapper():
        print('start')
        func()
        print('end')
    return wrapper

@decorator
def print_hello():
    print('hello')

print_hello()
```

#### 실행 결과
```
start
hello
end
```

### 2. `@` 구문 사용하지 않고 호출하기.
```python
def decorator(func):
    def wrapper():
        print('start')
        func()
        print('end')
    return wrapper

def print_hello():
    print('hello') 

decorated_hello = decorator(print_hello)

decorated_hello()
```

#### 실행 결과
```
start
hello
end
```

## 데코레이터를 여러 개 사용하면 어떻게 될까
- 아래의 예제를 보면 `print_hello()` 에 데코레이터가 두 개 붙어져 있다. 이럴 경우에는 위에서 부터 실행된다.
    - `decorator1(decorator2(print_hello))` 와 같다.
```python
def decorator1(func):
    def wrapper():
        print("decorator1")
        func()
    return wrapper

def decorator2(func):
    def wrapper():
        print("decorator2")
        func()
    return wrapper

@decorator1
@decorator2
def print_hello():
    print('hello')
```

#### 실행 결과
```
decorator1
decorator2
hello
```

## 원래 함수 이름이 안나올 땐 어떻게 할까
- 데코레이터를 여러 개 사용하게 되면, 데코레이터에서 반환된 `wrapper` 함수가 다른 데코레이터로 들어가게 된다. 따라서 함수의 이름(`__name__`)을 출력하면 `wrapper` 가 나온다.

```python
from functools import wraps

def decorator1(func):
    def wrapper():
        print("decorator1 : " + func.__name__)
        func()
    return wrapper

def decorator2(func):
    @wraps(func)
    def wrapper():
        print("decorator2 : " + func.__name__)
        func()
    return wrapper

@decorator1
@decorator2
def print_hello():
    print('hello')

print_hello()
```

#### 실행 결과
```
decorator1 : print_hello
decorator2
hello
```

---

[^1] https://docs.python.org/3/glossary.html#term-decorator
