# Error vs Exception
프로그램이 실행 중 어떤 원인에 의해서 오작동을 하거나 비정상적으로 종료되는 경우를 프로그램 오류라고 한다.<br>
프로그램 오류는 `Error` 와 `Exception` 으로 구분할 수 있다.

## Error
컴파일 시 문법적인 오류와 런타임 시 널포인트 참조와 같은 오류로 프로세스에 심각한 문제를 발생 시켜 프로세스를 종료 시킬 수 있다.<br>
즉, 메모리 부족이나 스택오버플로우와 같이 발생하면 복구할 수 없는 심각한 오류이다.

## Exception
문장이나 표현식이 문법적으로 올바르다 할지라도, 에러를 일으키고 싶다면 일으킬 수 있다.<br>
실행 중에 감지되는 오류들을 예외 라고 부르는데 예외는 무조건 치명적이지 않다.

즉, 발생하더라도 수습할 수 있는 비교적 덜 심각한 오류이다.<br>
에러의 상황을 예방하기 위해 예외 상황을 만들 수 있는데 이는 파이썬에서 try-exception 으로 예외 처리를 할 수 있다.

---

[^1] https://docs.python.org/ko/3/tutorial/errors.html<br>
[^2] https://stackoverflow.com/questions/60708789/exceptions-vs-errors-in-python
