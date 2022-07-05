# sort
> 지정한 파일의 내용을 **정렬해서 출력** 하는 command이다.<br>
> 또는 정렬된 파일을 합칠 때 사용한다.

### 기본 출력 예시
```bash
cat abc.txt
b
c
d
a

sort abc.txt
a
b
c
d
```

### 자주 사용되는 옵션
- `-r` : 역순으로 출력을 한다. 즉, 내림차순으로 정렬한다.
    ```bash
    sort -r [FileName] // file의 내용을 내림차순으로 정렬해서 출력한다.
    ```

- `-k` : 특정 필드를 기준으로 정렬한다.
    ```bash
    sort -k 2 [FileName] // file의 내용 중 2번째 필드를 기준으로 정렬해서 출력한다.
    ```

- `-u` : 정렬을 한 뒤 중복된 값은 제거한다.
    ```bash
    sort -u [FileName] // file의 내용을 정렬한 뒤 중복되는 값은 제거하고 출력한다.
    ```

- `-t` : 필드 구분자를 지정해서 정렬한다.
    ```bash
    sort -t , [FileName] // 필드를 , 로 구분해서 정렬한다. (첫번째 필드 값으로 정렬)

    sort -t , -k 2 [FileName] // 필드를 , 로 구분해서 2번째 필드로 정렬한다.
    ```

- `-f` : 대소문자를 구분하지 않고 정렬한다.
    ```bash
    sort -f [FileName] // file의 내용을 정렬하는데 대소문자를 구분하지않고 한다.
    ```

[^1] https://www.inflearn.com/course/command-line/dashboard
