# tr
> 어떤 내용을 **변환** 하는 명령어다.<br>
> 특정한 문자를 다른 문자로 변환하거나 제거하는데 사용된다.

### 기본 사용 예시
```bash
tr [option] SET1 [SET2] // SET1을 SET2로 바꾸기
```

### 자주 사용되는 옵션
- `-d` : SET1에서 지정한 문자를 제거한다.
```bash
echo "abcd EFGH igkl MNOP qrst" | tr -d [:lower:] // 소문자를 제거한다.
 EFGH  MNOP
```

- `-s` : SET에서 반복되는 문자를 제거한다.
```bash
echo "            a" | tr -s " " // 중복되는 공백을 지웠다.
 a

echo "            a" | tr -s " " -  // 중복되는 공백을 지우고 남은 공백 하나를 -로 변환했다.
-a
```

- SET
    - `char1-char2` : char1부터 char2까지 ('a-z')
    - `[:alnum:]` : 문자 + 숫자
    - `[:alpha:]` : 문자
    - `[:blank:]` : 공백
    - `[:space:]` : 공백 + newline
    - `[:digit:]`, `[:xdigit:]` : 10진수 숫자, 16진수 숫자
    - `[:lower:]`, `[:upper:]` : 소문자, 대문자