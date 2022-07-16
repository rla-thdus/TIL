## Lambda란
프로그래밍 언어에서 사용되는 개념으로 익명의 함수, 이름 없는 함수를 지칭하는 용어이다.<br>
파이썬에서는 보통 `def` 를 사용해서 함수를 선언하고 기능을 정의하는 것과 다르게, 람다는 함수를 하나의 식으로 정의한다.

### 기본 구조
```python
lambda 파라미터 : 표현식

# ex)
lambda x: x + 2
```

## Def 함수와 Lambda 함수의 차이
### 1. lambda는 return 키워드를 사용하지 않는다.
- 람다 함수는 결과를 return을 사용하지 않고 자동으로 반환해준다. 그에 반해 def 함수에서 결과를 반환받고 싶으면 return을 사용해야 한다.

```python
# def 로 만든 함수
>>> def sum(a, b):
...     return a + b
>>> sum(1, 2)
3

# lambda로 만든 함수
>>> sum_by_lambda = lambda a, b: a + b
>>> sum_by_lambda(1, 2)
3
```

### 2. lambda로 만든 경우에는 함수에 이름이 없다.
- 아래의 코드를 보면 알 수 있듯이 def를 통해 만들어진 함수는 이름이 있는데, lambda를 통해 변수에 할당한 함수는 이름이 lambda로만 나온다.

```python
# def 로 만든 함수
>>> def sum(a, b):
...     return a + b

# lambda로 만든 함수
>>> sum_by_lambda = lambda a, b: a + b

# 함수 이름 출력
>>> print(sum.__name__)
sum
>>> print(sum_by_lambda.__name__)
<lambda>
```

## 그럼 def 와 lambda는 각각 언제 사용하는게 유리할까
def는 재사용이 필요한 함수를 만들 때 사용하고, lambda는 간단한 일회성 함수를 만들고 싶을 때 사용하는게 좋다.

---

[^1] https://docs.python.org/3/glossary.html#term-lambda