# Generator란
> ### Iterator를 생성해주는 함수이다.
> Iterator는 `next()` 메서드를 사용해서 데이터에 순차적으로 접근이 가능한 객체이다.<br>
> 함수 안에서 `yield` 를 사용해서 Generator를 만들 수 있다.

#### yield란
일반 함수와 generator 함수를 구분할 수 있는 핵심적인 부분이다. generator 함수를 실행하다가 `yield` 를 만나면 그 상태로 정지하면서 값은 `next()` 를 호출한 곳에 전달하고 그 상태를 유지한다. 그리고 다시 실행이 되면 `yield` 의 다음 코드부터 실행된다.

## Generator Expression
Generator 함수를 좀 더 쉽게 사용하기 위해서 Generator Expression을 제공한다.<br>
list comprehension과 비슷하지만, `중괄호 []` 가 아닌 `소괄호 ()` 를 사용한다.

```python
>>> (i for i in range(10))
<generator object <genexpr> at 0x7f1b09af0f90>  # generator object로 생성된 걸 확인할 수 있다.
```

## Generator를 사용하는 이유
### 1. 메모리를 효율적으로 사용할 수 있다.
- list와 generator로 생성했을 때, 각각의 메모리 결과를 보면 알 수 있다.
    - 아래의 결과를 보면 list로 생성했을 때는 사이즈가 커질 수록 메모리 사용량이 늘어나고 있다.
    - 반면에 generator는 사이즈가 커지더라도 메모리 사용량은 일정하다.
```python
>>> import sys
>>> sys.getsizeof([i for i in range(10)])
184
>>> sys.getsizeof([i for i in range(1000)])
8856
>>> sys.getsizeof((i for i in range(10)))
112
>>> sys.getsizeof((i for i in range(1000)))
112
```

> #### 🧐 왜 generator는 사이즈가 커져도 메모리 사용량이 동일한걸까
> list는 안에 속한 모든 데이터를 메모리에 적재하기 때문에 사이즈가 커질 수록 메모리 사이즈도 커지게 된다. 하지만 generator의 경우에는 데이터 값을 한 번에 모든 데이터를 메모리에 적재하는게 아니라 `next()` 메소드를 통해 차례로 값에 접근할 때 마다 적재하는 방식이다.

### 2. Lazy evaluation, 계산 결과 값이 필요할 때 까지 계산을 늦추는 효과를 얻을 수 있다.
- list와 generator로 1초간 sleep을 실행하는 함수를 사용하면 알 수 있다.
    - list는 list comprehension의 모든 값을 먼저 수행하기 때문에 sleep_func 함수를 n 만큼 반복 실행하고 반복문을 수행한다.
    - 반면 generator는 반복문이 한 번 동작할 때, sleep_func 함수로 값을 하나씩 받아온다.
```python
# 1초간 sleep 실행하는 함수
>>> from time import sleep
>>> def sleep_func(n):
...     print("sleep 1 sec")
...     sleep(1)
...     return n

# list 사용
>>> for item in [sleep_func(n) for n in range(5)]:
...     print(item)
sleep 1 sec
sleep 1 sec
sleep 1 sec
sleep 1 sec
sleep 1 sec
0
1
2
3
4

# generator 사용
>>> for item in (sleep_func(n) for n in range(5)):
...     print(item)
sleep 1 sec
0
sleep 1 sec
1
sleep 1 sec
2
sleep 1 sec
3
sleep 1 sec
4
```

> #### 🧐 generator의 Lazy evaluation이 왜 좋은걸까
> 만약 sleep_func 함수가 아닌 연산이 복잡하고 오래걸린다고 가정을 하면 리스트의 경우에는 그 연산이 n번 동작하기 전까지 반복문을 수행하지 않는다. 반면에 generator는 한 번 복잡한 연산을 수행하고 나서 반복문을 수행하기 때문에 값이 다시 필요해지는 순간이 오기 전까지 연산을 늦출 수 있다.

---

[^1] https://docs.python.org/3/glossary.html#term-generator<br>
[^2] https://docs.python.org/3/glossary.html#term-generator-iterator<br>
[^3] https://docs.python.org/3/reference/expressions.html#grammar-token-python-grammar-yield_expression<br>