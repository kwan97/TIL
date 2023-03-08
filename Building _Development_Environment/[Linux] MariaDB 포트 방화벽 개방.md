# [Linux] MariaDB 포트 방화벽 개방

설치 환경: **Rocky Linux 8**

---

```bash
sudo dnf install firewａlld
sudo systemctl enable firewalld
sudo systemctl disable firewalld
sudo systemctl start firewalld
sudo systemctl stop firewalld
```

```bash
# firewall-cmd --permanent --zone=public --add-port=[포트번호 또는 포트범위]/[프로토콜]
sudo firewall-cmd --permanent --zone=public --add-port=8080/tcp
sudo firewall-cmd --permanent --zone=public --add-port=8000-9000/tcp
# firewall-cmd --permanent --zone=public --remove-port=[포트번호]/[프로토콜]
sudo firewall-cmd --permanent --zone=public --remove -port=8080/tcp
sudo firewall-cmd --list-ports
```

```bash
# 재기동
sudo firewall -cmd --reload
```
