# json.loads()
json 문자열을 파이썬 객체로 변환할 때 사용한다.<br>
주로 파일에 저장되어 있는 json 문자열을 읽거나 HTTP request body 읽을 때 사용된다.

```python
import json

json_string = '''{
    "name": "소연",
    "age": 20,
    "blood_type": "A"
}'''

json_object = json.loads(json_string)

assert json_object['age'] == 20
assert json_object['blood_type'] == "A"
```

# json.dumps()
파이썬 객체를 json 문자열로 변활할 때 사용한다.

```python
import json

json_object = {
    "name": "소연",
    "age": 20,
    "blood_type": "A"
}

json_string = json.dumps(json_object)
print(json_string)
----------------------------------------------
{"name": "소연", "age": 20, "blood_type": "A"}
```

default로 변환되는 json 문자열은 한 줄로 나오기 때문에, 파이썬 객체가 많은 데이터를 가지고 있다면 가독성이 떨어진다.<br>
이 경우 `indent` 파라미터 값을 넘겨서 들여쓰기를 해서 json 문자열을 반환할 수 있다.

```python
json_string2 = json.dumps(json_object, indent=2)
print(json_string2)
---------------------------------------------------
{
  "name": "소연",
  "age": 20,
  "blood_type": "A"
}
```

---

[^1] https://docs.python.org/ko/3/library/json.html<br>
[^2] https://stackoverflow.com/questions/32911336/what-is-the-difference-between-json-dumps-and-json-load
