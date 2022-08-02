# Argument(전달 인자)와 Parameter(매개 변수)의 차이
### argument는 함수를 호출할 때 실제로 함수에 전달하는 값을 말한다.
- 함수 호출부에서 괄호로 묶인 것이 `argument` 이다.

### parameter는 함수를 정의할 때 함수에서 받는 인자의 이름을 말한다.
- 함수 선언부에서 함수 이름 뒤에 괄호로 묶여 표현하는 것을 `parameter` 라고 한다.

### 코드 예시
```python
def introduce(age, name):
    print('안녕하세요. 저는 {}살 {}입니다.'.format(age, name))

introduce(100, '김소연')
```

여기에서 parameter는 age와 name을 나타내고, argument는 100, 김소연을 나타낸다.
