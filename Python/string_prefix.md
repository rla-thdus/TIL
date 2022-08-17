# string prefix
> ### 문자열 앞에 r, u, b, f 같은 알파벳이 붙는 걸 말한다.

## r - raw
- 모든 escape 문자를 그대로 출력한다.

```python
>> print(r"hi\nhello\tI'm fine thank you")
hi\nhello\tI'm fine thank you

>> print("hi\nhello\tI'm fine thank you")
hi
hello   I'm fine thank you
```

## u - unicode
- python2에서 사용되던 syntax다.
- python3은 default encoding이 unicode이기 때문에 굳이 붙이지 않아도 된다.

```python
>> u"this is same" == "this is same"
True
```

## b - bytes
- 우리가 다루는 데이터들은 특정 인코딩을 거처 바이트로 변환이 되고, 다시 필요할 때 사람이 알아볼 수 있게 디코딩을 한다.
- 바인트인데 출력할 땐 앞에 b가 붙은 거 말곤 차이가 없는 이유는 사람에게 보여주기 위해서 임의로 디코딩된 결과여서 그렇다.
    - 하지만 이게 바이트라고 명시해주기 위해 앞에 `b` 가 붙어있다.

```python
>> _str = "string"
>> _btye = b"string"
>> print(_str)
"string"
>> print(_byte)
>> b"string"
```

## f - format
- 전에 문자열을 포맷시킬 때 `.format()` 을 사용했다.
- 3.6 이후로는 아래처럼 사용 가능하다.

```python
>> name = "rla_thdus"
>> age = 1000
>> print(f"hi! my name is {name}. I'm {age} years old.")
hi! my name is rla_thdus. I'm 1000 years old.
```

---

[^1] https://docs.python.org/3/reference/lexical_analysis.html#string-and-bytes-literals<br>
[^2] https://stackoverflow.com/questions/2592764/what-does-a-b-prefix-before-a-python-string-mean<br>
[^3] https://stackoverflow.com/questions/2464959/whats-the-u-prefix-in-a-python-string/2464968#2464968<br>
[^4] https://stackoverflow.com/questions/54533637/rstring-bstring-ustring-python-2-3-comparison
