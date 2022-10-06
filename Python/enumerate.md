# enumerate()
인덱스와 원소에 동시에 접근하면서 반복을 돌릴 수 있는 파이썬 내장 함수이다.for 문의 in 뒤에 enumerate 함수로 감싸서 사용하면 된다.<br>
`enumerate()` 는 기본적으로 인덱스와 원소로 이루어진 튜플을 만들어 준다. 따라서 인덱스와 원소를 각각 다른 변수에 할당하고 싶다면 언패킹을 해줘야 한다.

```python
for i in enumerate(['first', 'second', 'third']):
    print(i)
    
(0, 'first')
(1, 'second')
(2, 'third')
```

```python
for n, i in enumerate(['first', 'second', 'third']):
    print(n, i)

0 first
1 second
2 third
```

## 시작 인덱스 변경
반복을 돌리다보면 인덱스를 0이 아니라 1부터 시작하고 싶을 때가 가끔 있다. 이럴 때는 start 인자에 시작하고 싶은 인덱스 숫자를 넘기면 된다.

```python
for n, i in enumerate(['first', 'second', 'third'], start=1):
    print(n, i)

0 first
1 second
2 third
```

# enumerate()를 사용하는 이유
enumerate()를 사용하면 range()를 사용할 때 처럼 len()을 이용해서 인덱스를 돌리는 번거로운 일이 없고 직접 인덱스로 접근해서 원소를 찾아내는 일도 없어지기 때문이다.

---

[^1] https://docs.python.org/3/library/functions.html#enumerate<br>
[^2] https://stackoverflow.com/questions/22171558/what-does-enumerate-mean
