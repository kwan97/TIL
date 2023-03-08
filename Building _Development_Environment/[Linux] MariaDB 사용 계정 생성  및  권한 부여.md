# [Linux] MariaDB 사용 계정 생성 및 권한 부여

설치 환경: **Rocky Linux 8**

---

```bash
# 보안스크립트로 MariaDB 로그인
sudo mariadb-secure-installation
```

```sql
-- CREATE USER '사용자ID'@'%' IDENTIFIED BY '패스워드';
CREATE USER 'testuser'@'%' IDENTIFIED BY 'testpwd';
SELECT User, Host FROM mysql.user;

-- create database [생성할 DB명]
CREATE DATABASE testdb;
SHOW DATABASES;

-- DB접근 권한 부여
-- GRANT ALL PRIVILEGES ON [특정DB.* 또는 *.*]to'[사용자ID]'@'%';
GRANT ALL PRIVILEGES ON testdb.*TO'testuser'@'%';
GRANT ALL PRIVILEGES ON *.*TO'testuser'@'%';

-- 변경된 권한 적용
FLUSH PRIVILEGES;

-- 계정/권한 삭제
-- DROP USER ‘사용자ID’@'IP 또는 %';
DROP USER 'testuser’@'192.168.100';
-- REVOKE ALL ON *.* FROM '계정명'@'접속 위치';
REVOKE ALL ON *.* FROM ‘testuser’@’192.168.100’;
```
