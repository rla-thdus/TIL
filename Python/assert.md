# assert
가정 조건문이라고 불리는 assert는 조건문이 True가 아닐 경우에 `AssertionError` 를 일으킨다.<br>
지금까지 잘 움직이던 코드이지만, 추가로 코드를 작성했을 때 예상하지 못한 다른 동작을 하게 될 경우 assert를 사용해 빠르게 방지할 수 있다.


## 사용 방법
```python
assert [조건식], [조건식이 False 일 경우 출력될 메시지]
```

[조건식] : 이 조건이 참이면 코드가 그대로 진행되고, 거짓이면 AssertionError 가 발생한다.<br>
[조건식이 False 일 경우 출력될 메시지] : 앞에 조건이 거짓인 경우 AssertionError 와 함께 남길 메시지다.

# assert 를 사용했을 때 장점
1. 코드 앞 부분에 만족해야 할 조건들을 한번에 몰아서 검사할 수 있다.
2. 검사해야 할 조건이 여러 개인 경우, 가독성이 향상되고 디버깅이 편해질 수 있다.
3. 코드 실행 부가 길어질 경우, 조건 검사를 앞으로 따로 빼면서 2번 장점이 더해진다.

---

[^1] https://docs.python.org/3/reference/simple_stmts.html#assert<br>
[^2] https://stackoverflow.com/questions/5142418/what-is-the-use-of-assert-in-python
