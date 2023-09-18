---
title: Apache Bigtop 을 통한 Apache Ambari 설치 - 1
author: jihun.eu
date: 2019-09-17 15:00:00 +0900
categories: [Bigdata, Install]
tags: [Bigdata]
render_with_liquid: true
---

## 배경

1. Hadoop-ecosystem 구성 편의성 확보를 위해 Apache Ambari 선정
2. Apache Ambari 설치는 Apache Bigtop 을 통해 진행

### Apache Ambari?

Hadoop-ecosystem 관리 편의성을 위해 배포, 관리, 모니터링 소프트웨어.  
Hortonworks 사에서 개발했으며, 2018 년 Cloudera 합병 이후 개발 중단됨.  
2023-09-17 기준 최신 버전 `2.8.0`

> 합병 이후 Ambari + HDP, Hortonworks Data Platform pack 사용 불가로 인해 Apache Bigtop 을 통해 Ambari 구성하기로 결정

### Apache Bigtop?

Apache 재단의 Hadoop-ecosystem 패키징, 테스팅, 가상화 지원 프로젝트.  
2023-09-17 기준 최신 버전 `3.2.1`

#### 빌드 가능한 서비스

<https://cwiki.apache.org/confluence/display/BIGTOP/Bigtop+3.2.1+Release>

```txt
bigtop 3.2.0 stack includes the following components
alluxio                        2.8.0
bigtop-ambari-mpack            2.7.5
bigtop-groovy                  2.5.4
bigtop-jsvc                    1.2.4
bigtop-utils                   3.1.0
flink                          1.15.3
gpdb                           5.28.5
hadoop                         3.3.5
hbase                          2.4.13
hive                           3.1.3
kafka                          2.8.1
livy                           0.7.1
oozie                          5.2.1
phoenix                        5.1.2
solr                           8.11.2
spark                          3.2.1
tez                            0.10.1
ycsb                           0.17.0
zeppelin                       0.10.1
zookeeper                      3.5.9
```

Apache Bigtop `3.0.0` 버전 이후부터 Apache Ambari `2.7.5` 버전 지원

#### 지원 환경

```txt
CentOS 7 (for x86_64 and aarch64 only)
Rocky Linux 8 (for x86_64 and aarch64 only)
Fedora 36
Debian 10 (for x86_64 and aarch64 only)
Debian 11
Ubuntu 20.04
Ubuntu 22.04
```

### Reference

* <https://www.bearpooh.com/178>
* <https://snowturtle93.github.io/posts/Apache-Bigtop%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-Ambari-%EC%84%A4%EC%B9%98-%EB%B0%8F-Hadoop-%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0-%EA%B5%AC%EC%B6%95/>
* <https://ambari.apache.org/>
* <https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=27825348>