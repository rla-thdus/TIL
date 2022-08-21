# awk
> **데이터를 원하는 포맷대로 쉽게 가공** 할 수 있게 해주는 명령어다.

### 사용 예시
```bash
awk [option] [awk program] [argument]

# awk program의 구조는 다음과 같다.
pattern {action}

awk [option] 'pattern {action}' [argument]
```

### 주요 내장 변수
```text
$1, $2, $3 - Nth field
NR - number of records
NF - number of fields
FS - field separator (default white space)
RS - record separator (default new line)
OFS - Output field separator
ORS - Output record separator
```

### 자주 사용되는 옵션
- `-F` : 필드 구분자를 지정한다.
```bash
$ tail /etc/passwd | awk -F: '/usr/ {print $1}'
_demod
_rmd
_accessoryupdater
_knowledgegraphd
_coreml
_sntpd
_trustd
_darwindaemon
_notification_proxy
_oahd
```

---

[^1] https://www.inflearn.com/course/command-line/dashboard
