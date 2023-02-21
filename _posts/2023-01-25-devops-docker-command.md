---
layout: post
title:  "도커(Docker) - 기본 명령어"
crawlertitle: "About Docker Command"
summary: "Docker"
date:   2023-01-25 10:00:00 +0900
categories: posts
tags: ['DevOps']
author: Yeonghyeon Kim
---

다음 명렁어를 사용하여 도커(Docker)를 사용해봅니다.

### 이미지(Image)

#### 이미지 검색

```bash
 docker search [이미지명]
```

#### 이미지 다운로드

```bash
 docker pull [이미지명]:latest
```

#### 이미지 목록 표시

```bash
 dokcer images
```

#### 이미지 삭제

```bash
docker rmi [이미지ID]
```

### 컨테이너(Container)

#### 컨테이너 생성

```bash
 docker run [이미지명]
```

### 컨테이너 접속

```bash
docker exec -it  [컨테이너ID] /bin/bash
```

#### 컨테이너 생성과 동시에 접속

```bash
 docker run -it -p  [Host(Port)]:[Docker(Port)] [이미지명] /bin/bash
```

#### 컨테이너 목록 표시

* 현재 가동중인 컨테이너만 표시

```bash
 docker ps
```

* 모든 컨테이너 표시

```bash
 docker ps -a
```

#### 컨테이너 명령 실행

```bash
 docker exec -it [컨테이너ID] [사용할 명령어]
```

#### 컨테이너 삭제

```bash
docker rm [컨테이너 ID]
```
