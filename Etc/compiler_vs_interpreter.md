# 컴파일러가 하는 일
고급 프로그래밍 언어로 작성된 코드를 런타임 이전에 기계어로 변환하는 프로그램이다.<br>
즉, 사람이 읽는 코드를 기계가 읽을 수 있는 코드로 바꿔준다.

코드 전체를 한 번에 번역하여 번역한 결과를 컴퓨터가 실행할 수 있는 목적 프로그램으로 저장한다.

문법 에러가 있으면 컴파일 단계에서 발견하게 되며, 이를 컴파일 에러라고 한다. 컴파일 에러가 발생하면 실행이 안된다.<br>
따라서 컴파일 에러와 관련된 에러를 초기에 발견할 수 있다.

> 컴파일 하기 전의 코드를 **소스 코드**, 컴파일 된 코드를 **목적 코드** 라고 한다.

## 장점
- 기계어이기 때문에 코드가 유출되지 않는다.
- 컴파일이 완료된 실행 파일은 빠르게 실행한다.
- 컴파일 에러와 관련된 에러를 초기에 발견할 수 있다.

## 단점
- 코드를 수정하면 다시 컴파일 해야 한다.
- 전체를 컴파일 해야 하기 때문에 용량이 크다.
- 한 번에 번역하기 때문에 컴파일링 시간은 비교적 느리다.
- 목적 프로그램을 생성하기 위해 메모리를 사용한다.

# 인터프리터가 하는 일
런타임 이후에 한 줄씩 번역하며 코드를 바로 실행하는 프로그램이다.

## 장점
- 전체를 컴파일하지 않기 때문에 디버깅에 유리하다.
- 바로 실행되기 때문에 목적 프로그램이 생성되지 않는다.

## 단점
- 실행 속도가 컴파일러에 비해서 느리다.
- 바이트 코드로 번역되기 때문에 프로그램의 코드가 유출될 수 있다.

# 컴파일러와 인터프리터의 차이
컴파일러는 한꺼번에 컴파일을 하기 때문에 컴파일 시간은 오래 걸리지만 목적 프로그램을 실행할 때는 컴파일을 하지 않아 속도가 월등히 빠르다.<br>
인터프리터는 라인별로 번역하기 때문에 컴파일 하는 시간이 짧지만 실행까지의 시간까지 합친다면 컴파일러보다 전체적인 속도는 느리다.

||컴파일러|인터프리터|
|:---:|:---:|:---:|
|컴파일 단위|전체|한 줄|
|개발 편의성|코드를 수정할 때마다 다시 컴파일을 해야 해서 불편하다|코드 수정 후 바로 실행할 수 있어 편하다|
|컴파일 시간|전체를 컴파일 해야 해서 느리다|한 줄씩 컴파일 하기 때문에 빠르다|
|실행 시간|컴파일된 목적 프로그램을 바로 실행하면 돼서 빠르다|번역과 실행이 동시에 이뤄져 실행은 느리다|

---

[^1] https://stackoverflow.com/questions/2377273/how-does-an-interpreter-compiler-work?noredirect=1&lq=1<br>
[^2] https://cs.stackexchange.com/questions/84970/the-difference-between-compiler-and-interpreter
