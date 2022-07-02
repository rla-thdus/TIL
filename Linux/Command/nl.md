# nl
> **파일 내용을 라인 넘버와 함께 출력** 하는 command이다.<br>
> cat으로 파일 내용을 출력하는 느낌이지만 줄 번호가 같이 나오는 거다.

### 기본 출력 예시
아무런 옵션을 사용하지 않고 `nl` 를 사용했을 떄 출력 형식이다
```bash
1 Hello
2 Hi
3 Good
4 Great
```

### 자주 사용되는 옵션
- `-ba` : 공백에도 라인 넘버를 줘서 카운팅 한다.
    ```bash
    nl -ba [FileName] // file을 처음부터 끝까지 공백인 줄도 같이 카운팅 해서 출력한다.
    ```
- `-v N` : 시작 라인 넘버를 N으로 지정한다.
    ```bash
    nl -v 5 [FileName] // file의 시작 넘버가 5부터 출력된다.
    ```

[^1] https://www.inflearn.com/course/command-line/dashboard