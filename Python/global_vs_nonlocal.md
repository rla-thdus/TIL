# global 키워드
### 함수 안에서도 전역 변수의 값을 수정할 수 있게 한다.

아래의 코드를 실행하면 x의 값이 `20`이 출력된다고 생각할 수도 있지만 실제로는 `10`이 출력된다.<br>
함수 안의 `x` 라는 지역 변수와 함수 밖에 있는 `x`라는 전역 변수와는 엄연히 다른 변수이다.
```python
x = 10

def change_x():
    x = 20
    
change_x()
print(x)
```

그렇다면 함수 내부에서 전역 변수의 값에 영향을 주고 싶다면 어떻게 해야 할까?<br>
바로 `global` 을 사용하면 된다.
```python
x = 10

def change_x():
    global x
    x = 20
    
change_x()
print(x)
```

위의 코드를 실행하면 출력되는 x의 값이 `20`인 걸 확인할 수 있다.

# nonlocal 키워드
### 중첩 함수 내에서 비지역 변수를 수정할 수 있게 한다.

아래의 코드를 실행하면 x의 값이 `30`이 출력된다고 생각할 수도 있지만 실제로는 `20`이 출력된다.<br>
inner 함수 안의 `x` 라는 지역 변수와 inner 함수 밖에 있는 `x`라는 비지역 변수와는 엄연히 다른 변수이다.
```python
def outer():
    x = 20
    
    def inner():
        x = 30
        
    inner()
    print(x)
    
outer()
```

그렇다면 inner 함수 내부에서 비지역 변수의 값에 영향을 주고 싶다면 어떻게 해야 할까?<br>
바로 `nonlocal` 을 사용하면 된다.
```python
def outer():
    x = 20
    
    def inner():
        nonlocal x
        x = 30
        
    inner()
    print(x)
    
outer()
```

위의 코드를 실행하면 출력되는 x의 값이 `30`인 걸 확인할 수 있다.

### 📌 함수를 하나만 정의하고 global 변수에 영향을 주려고 하는 건 안된다
```python
x = 10

def change_x():
    nonlocal x
    x = 20
    
change_x()
print(x)
--------------------------------------
>>> no binding for nonlocal 'x' found
```

# global vs nonlocal
`global` 키워드는 일반 함수 내에서 전역(global/module) 변수를 대상으로 사용하는 반면에,<br>
`nonlocal` 키워드는 중첩 함수 내에서 비지역 변수를 대상으로 사용한다.

---

[^1] https://docs.python.org/3/reference/simple_stmts.html#the-nonlocal-statement <br>
[^2] https://docs.python.org/3/tutorial/classes.html#python-scopes-and-namespaces <br>
[^3] https://stackoverflow.com/questions/1261875/python-nonlocal-statement