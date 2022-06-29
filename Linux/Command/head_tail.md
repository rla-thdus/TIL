# head
> **문서 내용의 앞부분을 출력** 하는 command이다.<br>
> default로 10줄이 출력된다.

### 자주 사용하는 옵션
- `-n`, `--line` : Num line만 출력한다.

    ```bash
    head -n 15 [file] // 15줄 출력
    head -n -5 [file] // 문서 뒤에서 5줄 제외하고 전부 다 출력
    ```

- `-c`, `--byte` : Num byte만 출력한다. byte 입력시 K, M, G, T 입력 가능하다. 

    ```bash
    head -c 1 [file] // 문서 앞부분에서 한 글자 출력
    head -c -10M [file] // 문서 뒤에서 10M 제외하고 전부 출력
    ```

# tail
> **문서 내용의 뒷부분을 출력** 하는 command이다.<br>
> default로 10줄이 출력된다.

### 자주 사용하는 옵션
- `-n`, `--line` : Num byte만 출력한다.

    ```bash
    tail -n 15 [file] // 문서 뒤에서 15줄 출력
    tail -n +5 [file] // 문서 5번째 줄 부터 출력
    ```

- `-c`, `--byte` : Num line만 출력한다. byte 입력시 K, M, G, T 입력 가능하다. 

    ```bash
    tail -c 35 [file] // 문서 뒤에서 35 글자 출력
    tail -c +5 [file] // 문서 35번째 글자부터 출력
    ```

- `-f`, `--follow` : 추가되는 내용을 append해서 출력되게 한다.
- `-F` : 파일이 truncate 되는 경우 다시 열어서 follow한다. (logrotate 되는 파일에 유용)

    ```bash
    tail -f [file] // 문서 끝에 10줄이 나오고 나서 종료되는게 아니라 대기하면서 새로운게 추가될 때마다 출력된다.
    tail -F [file] // 문서가 지워졌다가 새로 생겨도 계속 follow 한다.
    ```
