# [Linux] MariaDB 설치

설치 환경: **Rocky Linux 8**

---

```bash
# Rocky Linux 시스템 업데이트
sudo dnf upgrade -refresh -y
```

```bash
# MariaDB 10.8 저장소 가져오기
sudo dnf install curl -y
curl -LsS https://downloads.mariadb.com/MariaDB/mariadb_repo_setup | sudo bash -s -- --mariadb-server-version=10.8
```

```bash
sudo dnf install mariadb-server mariadb
sudo dnf install mariadb-backup mariadb-devel -y
```

```bash
# 운영 관련 명령어
sudo systemctl enable mariadb --now
sudo systemctl disable mariadb
sudo systemctl start mariadb
sudo systemctl stop mariadb
sudo systemctl restart mariadb
sudo systemctl status mariadb
```
