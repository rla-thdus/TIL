# setUp() vs setUpClass()
이 둘의 차이점은 테스트가 두 개 이상 있을 때 나기 시작한다. `setUp()` 은 테스트케이스가 실행되기 전마다 실행되고<br>
`setUpClass()` 는 해당 클래스에서 테스트 시작시 한 번만 사용되며 초기 테스트 값 로딩이나 초기화를 주로 한다.

```python
import unittest

class ExampleTest(unittest.TestCase):
    @classmethod
    def setUpClass(cls):
        print("setUpClass")
        
    def setUp():
        print("setUp")
        
    def test1(self):
        print("test1")

    def test2(self):
        print("test2")
----------------------------------------
setUpClass
setUp
test1
.setUp
test2
```

tearDown과 tearDownClass도 마찬가지이다.

# setUpClass를 사용하는 이유
매번 테스트 케이스를 돌 때마다 데이터베이스와 연결하고, 파일 열고 등의 작업을 하게 되면 속도가 느려진다.<br>
이런 작업을 각각의 테스트 케이스마다 해야 한다면 `setUpClass`를 사용하게 되는 것 같다. 여러 번 수행하는 것을 한 번으로 해결 할 수 있기 때문이다.

---

[^1] https://docs.python.org/ko/3/library/unittest.html?highlight=setup#unittest.TestCase.setUpClass<br>
[^2] https://stackoverflow.com/questions/23667610/what-is-the-difference-between-setup-and-setupclass-in-python-unittest
