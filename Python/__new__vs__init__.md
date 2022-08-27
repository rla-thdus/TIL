## __init__메서드란
`__init__(initialize)`는 이름 그대로 인스턴스(객체)를 초기화 한다.<br>
다음과 같이 인스턴스를 만들 때 호출되는 매직 메서드이다.
```python
ksy = Person()
```

클래스 인스턴스에 속성을 부여하는 등 인스턴스 사용을 위한 초기 세팅을 해 준다.
```python
def __init__(self, name, age):
    self.name = name
    self.age = age
```

## __init__을 생성자라고 말할 수 있을까?
`__init__`을 대부분 생성자 메서드라고 한다. 하지만 `__init__` 메서드는 클래스 객체에 메모리를 할당하지 않는다.<br>
다시 말해 인스턴스를 생성하지 않는다는 말인데 과연 생성자라고 해도 되는 건지 의문이 생겼다.

실제로 메모리에 할당시키는 메서드는 바로 `__new__` 이다. 항상 `__init__`이 실행되기 전에 `__new__`가 실행되는데, 이때 객체에 메모리가 할당된다.<br>
`__new__` 가 객체를 생성해서 반환한다는 점에서 생성자에 더 맞는 것 같다는 생각도 들었지만 생성이란 것이 우리가 알고 있는 것과 다른 의미라고 한다.

여기서 생성이란 객체 생성 기능과는 다른, 인스턴스를 사용자가 원하는 대로 커스터마이징 하는 것을 말한다고 한다.<br>
예를 들어 `self.name=name` 과 같이 클래스 인스턴스에 속성을 부여하는 등 인스턴스 사용을 위한 초기 세팅을 하는 것이다.<br>

즉, `__init__` 이 클래스 인스턴스에 속성을 부여하는 등 인스턴스 사용을 위한 초기 세팅을 해주기 때문에 생성자라고 말하는 것 같다.

---

[^1] https://stackoverflow.com/questions/6578487/init-as-a-constructor<br>
[^2] https://stackoverflow.com/questions/674304/why-is-init-always-called-after-new <br>
[^3] https://www.reddit.com/r/learnpython/comments/2s3pms/what_is_the_difference_between_init_and_new <br>
[^4] https://www.pythonprogramming.in/how-to-use-new-and-init-in-python.html