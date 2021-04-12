# spring-boot-rest-library

A Spring boot application that uses hibernate, mariaDB docker, openssh-server to put files and Jsch library with a pool
connection.

## 1. Docker

Use the command below to build all containers.
```
docker-compose up
```

### 1.1 Maria DB

Configuration link: [maria DB docker](https://hub.docker.com/_/mariadb).

### 1.2 Linux server - openssh-server

Configuration link: [linux server openssh](https://docs.linuxserver.io/images/docker-openssh-server).

To access ssh server use command: 
```
ssh -i {PATH_TO_YOUR_PRIVATE_KEY} -p {PORT} {USER_NAME}@{SERVER_IP}
```

If your public key is not set inside ``authorized_keys`` into {VOLUME_PATH}/config/.ssh/authorized_keys

Insert your public key inside server: 
```
scp {PATH_TO_YOUR_PUBLIC_KEY} {VOLUME_PATH}/config/.ssh/authorized_keys
```

After to add the server to know_hosts you can connect with 
```
ssh -p {PORT} {USER_NAME}@{SERVER_IP}
```

## Pool connection Jsch library