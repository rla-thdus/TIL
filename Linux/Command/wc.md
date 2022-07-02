# wc
> **줄, 단어, byte 를 카운트** 해주는 command이다.<br>
> 단어를 구분하는 기준은 띄어쓰기다.

### 기본 출력 예시
아무런 옵션을 사용하지 않고 `wc` 를 사용했을 떄 출력 형식이다
```bash
 0  5 24 [FileName]
```

### 자주 사용되는 옵션
- `-l` : 라인수 만 출력한다.
    ```bash
    wc [FileName] // 해당 파일의 줄, 단어, byte 를 카운트 한다.
    wc -l [FileName] // 해당 파일의 줄의 수만 출력한다.
    wc -l *.json // 현재 디렉토리에서 파일 형식이 json인 파일 전부들의 줄의 수와 합계가 출력된다.
    ```

[^1] https://www.inflearn.com/course/command-line/dashboard