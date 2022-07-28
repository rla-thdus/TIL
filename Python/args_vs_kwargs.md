# *args
> ### 함수에서 여러 개의 인자를 받을 때 사용한다.
- *argument의 줄임말이다.
- `*args` 라고 사용하지 않고 원하는 단어로 사용할 수 있다.
- 몇 개의 인자를 받는지 정확히 모를 때 사용할 수 있다.
- n개의 인자를 튜플로 전달한다.

### 사용 예시
```python
def restaurant_menu(*Foods):
    for food in Foods:
        print(food)

restaurant_menu('짜장면', '짬뽕', '탕수육', '팔보채')
```

# **kwargs
> ### 함수에서 여러 개의 인자를 key-value 형태로 받을 때 사용한다.
- **keyword argument의 줄임말이다.
- `key=value` 형태로 함수를 호출할 수 있다.
- 딕셔너리 형태로 전달된다.

### 사용 예시
```python
def game_rank(**kwargs):
    for key, value in kwargs.items():
        print('{0} 님은 {1} 위 입니다.'.format(key, value))

game_rank(rlathdus=1,김소연=3,kimsoyeon=2)
```

## *args, **kwargs 와 함께 일반 변수를 인자로 받고 싶으면 어떻게 할까
우선 일반 변수와 함께 사용하고 싶다면 일반 변수를 맨 앞에서 명시해주고 그 뒤에 *args나 **kwargs를 넣어줘야 한다.

```python
def func(일반 변수, [*args or **kwargs])
```

### 왜 일반 변수를 맨 뒤에서 부르면 안될까
위에서 확인했듯이 *args와 **kwargs는 여러 개의 인자를 받을 때 사용한다. 해당 인자를 얼마나 받을지 모르는 상황에 맨 마지막에 일반 변수를 받으려고 하면 그 변수엔 값이 들어가지지 않는 상황이 일어날 수 있다.

## *args와 **kwargs를 동시에 사용할 때 어떤 걸 먼저 받아야 할까

---

[^1] https://legitcode267.tistory.com/13<br>
[^2] https://stackoverflow.com/questions/3394835/use-of-args-and-kwargs
