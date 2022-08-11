# sed
> **원본 텍스트 파일을 편집** 하는 명령어이다.<br>
> - 원본을 건드리지 않고 편집하기 때문에 작업이 완료되도 원본은 전혀 영향이 없다.
> - 수정, 치환, 삭제, 삽입 등 편집기 처럼 사용할 수 있지만 vi와 다른 점은 실시간이 아니라는 것이다.

### 사용 예시
```bash
$ sed [option] [File]
```

### 사용할 파일 내용
```text
appear
beside
crown
dragon
eagle
frank
gizzul
```

### 자주 사용되는 옵션
- `{RANGE}p` : 범위 내의 라인을 출력한다.
    ```bash
    $ sed -n 1,3p test.txt
  
    # 출력 결과
    appear
    beside
    crown
    ```
- `{RANGE}d` : 범위 내의 라인을 삭제한다.
    ```bash
    $ sed -n 1,3d test.txt # test.txt 파일의 1~3번 줄이 삭제된다.
    ```
  
- `/SEARCHPATTERN/p` : 검색 패턴과 매치되는 라인을 출력한다.
    ```bash
    $ sed -n /^a/p test.txt # a로 시작하는 행을 찾아 출력한다.
  
    # 출력 결과
    appear
    ```

- `/SEARCHPATTERN/d` : 검색 패턴과 매치되는 라인을 삭제한다.
    ```bash
    $ sed -n /^a/d test.txt # a로 시작하는 행을 찾아 삭제한다.
    ```

- `s/REGEX/REPLACE` : 정규식에 매치되는 부분을 REPLACE 로 교체한다.
    ```bash
    $ sed -n s/^a/bungee/ test.txt # a로 시작하는 행을 bungee로 교체한다.
    ```

[^1] https://www.inflearn.com/course/command-line/dashboard