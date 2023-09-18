---
title: Apache Bigtop 을 통한 Apache Ambari 설치 - 2
author: jihun.eu
date: 2019-09-17 16:00:00 +0900
categories: [Bigdata, Install]
tags: [writing]
render_with_liquid: true
---

## Bigtop 설치 전 요구사항

본 문서는 CentOS 7 를 기준으로 작성됨

### 1. hosts 설정

OS 공통 `/etc/hosts` 정보 기입

```sh
sudo vi /etc/hosts
```

다음 형식으로 정보 기입

```txt
[IPAddress] [HostName] ==> 기입

127.0.0.1 localhost ...
::1 localhost ...
```

### 2. Java 설치

#### CentOS 7

1. install java

    ```sh
    $ yum list java*jdk-devel
    ...
    Available Packages
    java-1.6.0-openjdk-devel.x86_64       1:1.6.0.41-1.13.13.1.el7_3        base
    java-1.7.0-openjdk-devel.x86_64       1:1.7.0.261-2.6.22.2.el7_8        base
    java-1.8.0-openjdk-devel.i686         1:1.8.0.382.b05-1.el7_9           updates
    java-11-openjdk-devel.i686            1:11.0.20.0.8-1.el7_9             updates
    java-11-openjdk-devel.x86_64          1:11.0.20.0.8-1.el7_9             updates
    $ yum install java-1.8.0-openjdk-devel.x86_64
    ...
    $ java -version
    openjdk version "1.8.0_372"
    OpenJDK Runtime Environment (build 1.8.0_372-b07)
    OpenJDK 64-Bit Server VM (build 25.372-b07, mixed mode)
    ```

2. JAVA_HOME 환경변수 설정

    ```sh
    $ readlink -f $(which java)
    /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.382.b05-1.el7_9.x86_64/jre/bin/java
    $ echo "export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.372.b07-1.el7_9.x86_64" >> ~/.bash_profile
    $ echo "export PATH=$PATH:$JAVA_HOME/bin" >> ~/.bash_profile
    ...
    $ source ~/.bash_profile
    $ echo $JAVA_HOME
    /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.372.b07-1.el7_9.x86_64
    ```
