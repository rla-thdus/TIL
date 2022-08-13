# call by assignment
> ### 파이썬이 함수에 인수를 전달하는 방식이다.
> - mutable object는 call by reference 방식으로, immutable object는 call by value의 형태로 변수를 핸들링한다.
> - call by object-reference 라고도 한다.

## mutable object
- list, dict, set 등의 객체이다.

### call by reference
함수 호출시 인자에 객체의 레퍼런스가 전달된다. 그래서 값이 바뀔 수도 있다.

## immutable object
- int, str, tuple 등의 객체이다. 

### call by value
함수 호출시 전달되는 값을 복사해서 함수의 인자로 전달된다. 그래서 내부에서 값의 변화가 있더라도 원본 값은 바뀌지 않는다.

---

[^1] https://stackoverflow.com/questions/986006/how-do-i-pass-a-variable-by-reference
