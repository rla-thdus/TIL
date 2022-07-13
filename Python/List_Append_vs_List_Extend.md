# append와 extend란
### append() 는 리스트 마지막에 요소를 추가한다.
- `list.append(item)` 은 리스트의 마지막에 인자로 전달된 item을 추가한다.
    - 아래의 결과에 보이는 것처럼 넣어준 item 그대로 리스트의 마지막에 추가해준다.

```python
>>> l1 = [1, 2, 3]
>>> l1.append('added')
>>> l1
[1, 2, 3, 'added']
>>> l1.append([4, 5, 6])
>>> l1
[1, 2, 3, 'added', [4, 5, 6]]
```

### extend() 는 모든 요소를 리스트에 추가한다.
- `list.extend(iterable)` 은 인자로 전달된 iterable의 모든 요소를 리스트에 추가한다. iterable이기 때문에 list, tuple 모두 가능하다.
    - 아래에 보이는 것 처럼 iterable한 객체의 각각의 항목을 리스트 끝에 하나씩 추가해준다.

```python
>>> l1 = [1, 2, 3]
>>> l1.extend('added')
>>> l1
[1, 2, 3, 'a', 'd', 'd', 'e', 'd']
>>> l1.extend([4, 5, 6])
>>> l1
[1, 2, 3, 'a', 'd', 'd', 'e', 'd', 4, 5, 6]
>>> l1.extend(("this is tuple", ))
>>> l1
[1, 2, 3, 'a', 'd', 'd', 'e', 'd', 4, 5, 6, "this is tuple"]
```

# list append 와 list extend 의 차이
### 1. extend는 iterable한 값만 올 수 있다.
- append는 어떤 자료형이 오더라도 상관 없지만 extend는 iterable하지 않은 값이 올 경우 TypeError가 난다.

```python
>>> l1 = [1, 2, 3]
>>> l1.extend(1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'int' object is not iterable
```

### 2. 리스트에 저장되는 방식이 다르다.
- append는 들어온 값 그대로 리스트의 끝에 추가를 해주지만, extend는 들어온 값의 각각의 항목을 리스트 끝에 하나씩 추가해준다.
```python
# append
>>> l1 = [1, 2, 3]
>>> l1.append(("this is tuple",))
>>> l1
[1, 2, 3, ('this is tuple',)]
# extend
>>> l2 = [1, 2, 3]
>>> l2.extend(("this is tuple", ))
>>> l2
[1, 2, 3, 'this is tuple']
```

---

[^1] https://docs.python.org/ko/3/library/array.html?highlight=append#array.array.append<br>
[^2] https://docs.python.org/ko/3/library/array.html?highlight=extend#array.array.extend
