## non-default value
```python
def non_default_value_func(year, month, day):
    print("오늘은 {}년 {}월 {}일이다.".format(year, month, day))
```
- 값이 정해지지 않음 인자이다.
- 함수를 호출할 때 인자를 순서대로 넣어줘야 한다.
- 인자에 어떤 타입이 들어올지 몰라서 가독성이 떨어진다.

## default value
```python
def default_value_func(name, hi="반가워"):
    print("안녕 난 {}이야. {}".format(name, hi))
```
- 함수 선언시 미리 기본 값이 정해지는 인자이다.
- 코드의 중복을 줄이고, 가독성을 높여준다.
- 기본 값이 정해져 있지만, 다른 값으로 바꿀 수 있다.

## 함수를 정의할 때 default value 를 non-default value 앞에 정의하면 안되는 이유
default value parameter 를 non-default value parameter 앞에서 지정하면 SyntaxError 가 나는 걸 볼 수 있다.

```python
def introduce(hi="안녕", name):
    print("{0}, 난 {1}이야.".format(hi, name))

introduce('김소연')
```

다음과 같이 나는 name에 값을 지정해줄 의도였지만, default value를 가진 파라미터도 값을 변경할 수 있기 때문에 hi에 값이 지정되게 된다. 따라서 name에는 아무런 값도 할당받지 못해서 에러가 나게 된다.

