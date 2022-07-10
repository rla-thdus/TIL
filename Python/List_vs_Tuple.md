### 차이를 알아보기 전에 둘의 공통점에 대해 알아보면 다음과 같다.
```python
>>> my_list = [1, 2, 3]
>>> type(my_list)
<class 'list'>
>>> my_tuple = (1, 2, 3)
>>> type(my_tuple)
<class 'tuple'>
```

- 리스트와 튜플 둘 다 컨테이너로 일련의 객체를 저장하는데 사용된다.
- 둘 다 타입과 상관없이 일련의 요소(element)를 가질 수 있다.
- 두 타입 모두 요소의 순서를 관리한다.

# 파이썬 List와 Tuple의 차이

### 1. List는 가변적(mutable)이고 Tuple은 불변적(immutable)이다.
```python
>>> my_list[1] = "two"
>>> my_list
[1, 'two', 3]
>>> my_tuple[1] = "two"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

#### 1-1) List에는 `.append()` 메소드를 사용해서 새로운 요소를 추가할 수 있지만, Tuple은 불가능하다.
- 애초에 튜플은 수정할 필요가 없기 때문에 `.append()` 메서드가 필요하지 않다.

### 2. 어떻게 사용하는지가 다르다.
- List는 단일 종류의 요소를 가지고 있고 그 일련의 요소가 몇 개나 들어 있는지 명확하지 않은 경우에 주로 사용한다.
- Tuple은 들어 있는 요소의 수를 정확히 알고 있을 경우에 사용한다.
    - 동일한 요소가 들어 있는 List와 달리 Tuple에서는 각 요소의 위치가 큰 의미를 가지고 있기 때문이다.

---

[^1] https://nedbatchelder.com/blog/201608/lists_vs_tuples.html