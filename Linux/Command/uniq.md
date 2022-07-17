# uniq
> **중복된 내용을 제거하고 출력** 하는 command이다.<br>
> default는 대소문자를 구별하면서 중복된 내용을 찾는다.

#### 사용할 파일 내용
```
cat abc.txt
Kim
KIM
kim
Lee
LEE
lee
Park
PARK
park
```

### 기본 사용 예시
```bash
uniq abc.txt
Kim
KIM
kim
Lee
LEE
lee
Park
PARK
park
```

### 자주 사용되는 옵션
- `-d` : 중복된 내용만 출력한다.
```bash
uniq -d [FileName]  // File에서 중복된 내용을 출력한다.
```

- `-u` : 중복되지 않은 내용만 출력한다.
```bash
uniq -u [FileName]  // file에서 중복되지 않은 내용만 출력한다.
```

- `-i` : 대소문자를 구별하지 않으면서 중복을 제거하고 출력한다.
```bash
uniq -i [FileName] // file의 내용을 대소문자 구별하지 않고 중복된 내용을 제거해서 출력한다.
```

---

[^1] https://www.inflearn.com/course/command-line/dashboard