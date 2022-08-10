# Docstring
> ### 클래스, 모듈 및 패키지에 대한 문서 역할이다.
> - python 객체의 `__doc__` 속성이나, `help()` 함수를 통해 접근할 수 있다.
> - 클래스, 모듈 및 패키지의 첫 줄에 위치한다.
> -  `'''` 또는 `"""` 으로 둘러싸여진 문자열이다.
>     - PEP8에서는 `"""` 을 권장하고 있다.

## Docstring Format
### One-Line Docstring
- 앞 뒤로 빈 줄을 만들면 안된다.
- 확장성을 위해서 한 줄이라도 `'''` 이나 `"""` 을 사용한다.

```python
def sum(a, b):
    """Returend the sum of argument a, b."""
    return a + b
```

### Multi-Line Docstring
- 여러 문장으로 구성되는데 보통 설명, 파라미터, 리턴 값으로 구성된다.
- 타입 힌트를 사용하고 있다면 굳이 같은 내용은 Docstring에서 반복하지 않아도 된다.

```python
def complex(real=0.0, imag=0.0):
    """Form a complex number.

    Keyword arguments:
    real -- the real part (default 0.0)
    imag -- the imaginary part (default 0.0)
    """
    if imag == 0.0 and real == 0.0:
        return complex_zero
    ...
```

# Docstring 과 주석의 차이는 뭘까
Docstring은 주석과 달리 여러 줄에 걸쳐서 작성할 수 있고, help() 함수를 통해 볼 수 있다는 차이가 있다.

---

[^1] https://peps.python.org/pep-0257/
