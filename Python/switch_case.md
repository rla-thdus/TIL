# 파이썬에 switch/case문이 없는 이유는 뭘까
`if~elif` 문의 가독성이 굉장히 좋고 switch/case문의 역할을 할 수 있기 때문이다. 그리고 `dict` 를 사용해서도 switch/case문을 비슷하게 사용할 수 있다.
그리고 파이콘 2007에서 switch에 대한 조사를 했을 때 사람들은 이 기능에 대해 크게 관심을 보이지 않았다.
이미 switch가 없어도 잘 동작하고 있어서 굳이 switch문을 추가할 필요성을 못느꼈기 때문이다.

## if~elif 사용
```python
num = input()

if num == "one":
    print(1)
elif num == "two":
    print(2)
elif num == "three":
    print(3)
else:
    print(0)
```


## dictionary 사용
```python
def switch(key):
    return {
        "one": 1,
        "two": 2,
        "three": 3
    }.get(key, 0)

num = input()
print(switch(num))
```

# if~elif와 dictionary를 사용한 방법 중 뭐가 더 추천하는 방법일까
일반적으로는 if~elif 사용을 더 권장한다. 하지만 조건이 많을 경우에는 사전과 함수를 매핑해서 사용하는 것을 권장한다. 상황에 따라서 더 편한 방법을 사용하면 될 것 같다.

---

[^1] https://peps.python.org/pep-3103/
