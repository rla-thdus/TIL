# DNS (Domain Name System)
> ### 도메인 이름을 IP 주소로 변환한다.
> - 도메인 이름과 IP 주소간의 매핑을 관리하여 마치 전화번호부 같은 느낌이다.
> - IP 주소를 외우기 쉬운 도메인으로 바꾸거나, 도메인을 다시 IP 주소로 바꿔주는 데이터베이스 시스템이다.

## DNS는 왜 나타나게 되었을까
- IP 주소를 다 외워서 다니기 어렵다.
- IP 주소가 바뀔 수 있는데, 그렇게 되면 바뀐 IP 주소로 다시 외워야 한다.

## DNS 동작 순서
- 브라우저의 검색 창에 `google.com` 을 입력한다.
- DNS에서 IP 주소(`172.217.161.206`)를 찾아 전달한다.
- 해당 IP 주소에 해당하는 웹 서버에 접속한다.

---

[^1] https://www.inflearn.com/course/http-%EC%9B%B9-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/dashboard<br>
[^2] https://aws.amazon.com/ko/route53/what-is-dns/
