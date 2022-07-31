# cut
> **지정된 파일 또는 파이프의 데이터에서 줄의 일부를 잘라내고 결과를 인쇄하는** command 이다.<br>
> 구분 기호, 바이트 위치 및 문자로 줄의 일부를 자를 때 사용할 수 있다.

### 사용 예시
```bash
cut [option] [file]
```

### 사용할 파일 내용
```
cat test.txt
a:b c d,e
f:g h i,j
k:l m n,o
p:q r s,t
```

### 자주 사용되는 옵션
- `-b` : byte를 기준으로 자른다.
```bash
cut -b 2 test.txt // 2번 째 바이트를 선택해서 출력한다.

# 출력 값
:
:
:
:
```

- `-c` : 문자열을 기준으로 자른다.
```bash
cut -c 5 test.txt // 5번 째 문자열을 선택해서 출력한다.

# 출력 값
c
h
m
r
```

- `-f` : 필드를 기준으로 자른다.
```bash
cut -f 1 test.txt // 잘라진 필드 1번 째 필드 값을 출력한다. 기본 구분자는 TAB이다.

# 출력 값
a:b c d,e
f:g h i,j
k:l m n,o
p:q r s,t
```

- `-d` : tab 대신 사용할 구분자를 지정한다.
```bash
cut -d: -f 2 test.txt // : 을 기준으로 구분해서 2번 째 필드 값을 출력한다.

# 출력 값
b c d,e
g h i,j
l m n,o
q r s,t
```

- `--output-delimiter=STRING` : 출력할 때 사용할 구분자를 지정한다.
```bash
cut -d ' ' -f 1,3 --output-delimiter="::" test.txt // 공백을 기준으로 1번부터 3번째 필드를 ::으로 구분하여 출력한다.

# 출력 값
a:b::d,e
f:g::i,j
k:l::n,o
p:q::s,t
```

---

[^1] https://www.inflearn.com/course/command-line/dashboard
