# hostnamectl
시스템의 호스트 네임을 관리할 수 있는 명령어로 옵션 없이 사용하거나 status 옵션을 주면 현재 정보를 출력합니다.

```shell
$ hostnamectl
Static hostname: centos7
Icon name: computer-vm
Chassis: vm
Machine ID: [machine id]
Boot ID: [boot id]
Virtualization: vmware
Operating System: CentOS Linux 7
CPE OS Name: cpe:/o:centos:centos:7
Kernel: Linux 4.18.0-240.el8.x86_64
Architecture: x86-64
```

호스트네임을 설정하려면 set-hostname 명령어 뒤에 설정할 호스트네임을 지정하면 된다.

```shell
$ sudo hostnamectl set-hostname centos7
```

---

[^1] https://www.lesstif.com/lpt/linux-hostname-105644119.html
