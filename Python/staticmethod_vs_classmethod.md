# Class Method
`@classmethod` 데코레이터를 사용해서 클래스에 메서드를 선언하면 해당 메서드는 클래스 메서드가 된다.<br>
첫 번째 매개 변수로는 클래스 인스턴스가 아닌 **클래스 자체** (cls) 가 넘어온다.

클래스 메서드는 이 `cls` 를 통해 클래스 속성에 접근하거나, 클래스 메서드를 호출할 수 있다.

```python
class X:
    @classmethod
    def Func(cls, ...):
        ...
```

# Static Method
`@staticmethod` 데코레이터를 사용해서 클래스에 메서드를 선언하면 해당 메서드는 정적 메서드가 된다.<br>
인스턴스 메서드나 클래스 메서드와 달리 첫 번째 매개 변수가 할당되지 않는다.

그렇기 때문에 정적 메서드에서는 인스턴스와 클래스 속성에 접근하거나 호출하는 것이 불가능하다.

```python
class X:
    @staticmethod
    def Func(...):
        ...
```

# Static Method 와 Class Method의 공통점
### 인스턴스를 만들지 않고 바로 클래스의 메서드를 실행할 수 있다.
```python
# static method
class Calculator:
    x = 10

    @staticmethod
    def add(num):
        return num + 10

print(Calculator.add(10))
---------------------------
>> 20

# class method
class Calculator:
    x = 10

    @classmethod
    def add(cls, num):
        return num + 10

print(Calculator.add(10))
---------------------------
>> 20
```

# Static Method vs Class Method
클래스 메서드를 호출할 때는 첫 번째 인자로 클래스 자체(cls)가 넘어오기 때문에<br>
클래스 속성에 접근하거나 다른 클래스 함수를 호출할 수 있다.

하지만 정적 메서드는 인스턴스 메서드, 클래스 메서드와 달리 첫 번째 인자에 아무것도 넘어오지 않기 때문에<br>
클래스 속성에 접근하는 것도 안되고, 클래스 함수를 호출하는 것도 할 수 없다.

---

[^1] https://docs.python.org/3/library/functions.html#classmethod<br>
[^2] https://docs.python.org/3/library/functions.html#staticmethod<br>
[^3] https://stackoverflow.com/questions/136097/difference-between-staticmethod-and-classmethod

