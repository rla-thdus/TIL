### 차이를 알아보기 전에 둘의 공통점에 대해 알아보면 다음과 같다.
#### 1. 컨테이너로 일련의 객체를 저장하는데 사용된다.
```python
my_list = [1, 2, 3]
my_tuple = (1, 2, 3)
```

#### 2. 타입과 상관없이 일련의 요소(element)를 가질 수 있다.
```python
my_list = [1, "이", [3]]
my_tuple = ("하나", (2), [3, 4])
```

#### 3. 인덱스를 통해 특정 요소에 접근할 수 있다.
```python
>>> my_list[0]
1
>>> my_tuple[1]
2
```

#### 4. iterable하다. 즉, for문에 넣고 돌릴 수 있다.
```python
for i in my_list:
   print(i)
  
for i in my_tuple:
  print(i)
```

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

### 2. List는 딕셔너리의 key값(해쉬값)으로 쓸 수 없지만, tuple은 가능하다.
```python
>>> my_list = [1, 2, 3]
>>> my_dict = {my_list: "My List"}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'

>>> my_tuple = (1, 2, 3)
>>> my_dict = {my_tuple: "My Tuple"}
>>> my_dict
{(1, 2, 3): 'My Tuple'}
```

#### 딕셔너리의 키 값은 immutable한 값만 올 수 있기 때문이다.
#### 하지만, 튜플에 리스트가 요소로 들어가 있다면 키 값으로 사용할 수 없다.
```python
>>> my_tuple = (1, 2, 3, [1, 2])
>>> my_dict = {my_tuple: "My Tuple"}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

### 3. List는 Identity가 다른 객체로 복사가 되고, Tuple은 Identity가 같은 객체로 복사된다.
- 즉 `is` 로 비교를 했을 때 List를 복사한 객체와 비교를 하면 False가 나오고, Tuple은 True가 나온다.
```python
>>> my_list = [1, 2, 3]
>>> my_list2 = my_list[:] # 다른 복사 방식 list(my_list)
>>> my_list is my_list2
False

>>> my_tuple = (1, 2, 3)
>>> my_tuple2 = my_tuple[:] # 다른 복사 방식 tuple(my_tuple)
>>> my_tuple is my_tuple2
True
```

#### 3-1) 그럼 왜 Tuple은 Identity가 같은 객체가 복사되는걸까?
아마도 메모리를 절약하고 성능을 높이기 위해서인 것 같다. Tuple은 immutable한 객체니까 값이 바뀔 일이 없다. 즉, 복사를 했을 때 원본 값이 바뀌었을 때 복사된 값도 함께 바꾸는 것에 대한 걱정을 할 필요가 없다는 뜻이다. 그래서 객체를 굳이 복사하지 않고 기존의 객체에 변수만 할당하는 방법으로 효율을 높이는 것 같다.

---

[^1] https://nedbatchelder.com/blog/201608/lists_vs_tuples.html