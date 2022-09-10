# pass
반복문 수행에 있어서 전혀 영향을 끼치지 않는다.

pass가 사용되는 경우는
1. 조건문에서 넣어줄 조건이 딱히 없을 경우
2. class 선언할 때, 초기에 넣어줄 값이 없을 경우

일단 코드를 작성한 후 동작 확인을 위해서 실행할 때, 해당 부분에서 오류가 발생하지 않도록 하기 위해 많이 사용한다.

### 사용 예시
```python
for i in range(10):
    if i % 2 == 0:
        pass
        print(i)
    else:
        print(i)

--------------------
0
1
2
3
4
5
6
7
8
9
```

# continue
아래 코드를 건너뛰고 다음 순서의 반복을 수행한다.

### 사용 예시
```python
for i in range(10):
    if i % 2 == 0:
        continue
        print(i)
    else:
        print(i)

--------------------
1
3
5
7
9
```

---

[^1] https://stackoverflow.com/questions/9483979/is-there-a-difference-between-continue-and-pass-in-a-for-loop-in-python
