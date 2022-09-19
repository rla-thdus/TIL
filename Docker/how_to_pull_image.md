# docker image pull
```shell
$ docker image pull [OPTIONS] NAME[:TAG|@DIGEST]
```

특정 버전을 같이 적어주지 않으면 자동으로 최신 버전으로 다운받는다.

### OPTIONS

|options|description|
|:---:|:---|
|`--all-tags`, `-a`|리포지토리에서 태그가 지정된 모든 이미지 다운로드 하기|
|`--disable-content-trust`|이미지 확인 건너뛰기|
|`--platform`|서버가 다중 플랫폼을 지원하는 경우 플랫폼 설정하기|
|`--quiet`, `-q`|자세한 출력 하지않기|

# 이미지는 어디서 받아오는 걸까
`docker image pull` 명령어를 사용할 때는 사실상 이미지 이름 앞에 docker hub에서 내려받겠다는 것이 디폴트로 적용되어 있다.<br>
따라서 docker hub가 아닌 별도의 저장소에서 받고 싶다면 이미지 이름 앞에 url을 지정해주면 된다.

---

[^1] https://docs.docker.com/engine/reference/commandline/image_pull/
