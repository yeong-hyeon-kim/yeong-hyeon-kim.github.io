---
layout: post
title:  "깃(Git) 튜토리얼"
crawlertitle: "Tutorial Git"
summary: "Tutorial Git "
date:   2023-02-04 10:00:00 +0900
categories: posts
tags: ['Git']
author: Yeonghyeon Kim
---

깃(Git)을 사용해봅니다.

## 1. 깃(Git) 설치

[이곳을 선택하여 다운로드 합니다.](https://git-scm.com/)

## 2. 저장소 공유

- CLONE(클론)
  - 원격 저장소를 복제합니다.
- FETCH(패치)
  - 원격 저장소의 변경 내용을 병합하지 않고 확인만 합니다.
- PUSH(푸시)
  - 로컬 저장소의 변경 내용을 원격 저장소에 업로드합니다.
- PULL(풀)
  - 원격 저장소의 변경 내용을 로컬 저장소에 다운로드합니다.
- MERGE(머지)
  - 원격 저장소의 변경 내용을 로컬 저장소에 갱신합니다.
​

## 3. 브랜치(Branch)

동일한 소스코드 버전을 기반으로 동시에 다양한 작업을 할수 있게 만들어 주는 기능입니다.
​

### 브랜치 만들기

``` bash
  git branch [브런치 이름]
```

### 브랜치 이동하기

``` bash
  git checkout [브런치 이름]
```

### 브랜치 병합하기

```bash
  git merge [브런치 이름]
```

### 브랜치 삭제하기

```bash
  git branch -d [브런치 이름]
```

## 4. 태그(Tag)

​
커밋을 알아보고 쉽도록 이름을 붙이는 것을 말합니다.
​

### 일반 태그(Lightweight Tag)

- 이름만 붙일 수 있습니다.
- 토픽 브런치(Topic Branch)에서 주로 사용합니다.

```bash
  git tag [태그 이름]
```

### 주석 태그(Annotated Tag)

- 이름, 설명, 서명, 저자, 날짜
- 릴리즈 브런치(Release Branch)에서 주로 사용합니다.

```bash
git tag -a [태그 이름] -m [태그 주석]
```

### 태그 삭제하기

```bash
git tag -d [태그 이름]
```

## 5\. 스태시(Stash)

​
커밋 전 브랜치 이동 시 변경사항을 임시로 저장하는 공간 입니다.
​

### 스태시 저장

```bash
git stash [스태시 이름(선택)]
```

### 스태시 목록

```bash
git stash list
```

### 스태시 가져오기

```bash
git stash pop
```

```bash
git stash apply stash@{N}
```

## 6. 커밋 변경

### 이전에 작성한 커밋 수정

```bash
git add [수정된 파일명]
```

```bash
git commit --amend
```

### 커밋 초기화(Reset)

#### Soft

```bash
git reset --soft HEAD~~
```

#### Mixed

```bash
git reset --mixed HEAD~~
```

#### Hard

```bash
git reset --hard HEAD~~
```

​
변경 함 - ✅ 변경 안 함 - ❌

|Mode|HEAD 위치|인덱스|작업트리|사용|
|---|:---:|:---:|:---:|:---|
|SOFT|✅|❌|❌|커밋만 되돌릴 때|
|MIXED|✅|✅|❌|인덱스를 원래대로 되돌릴 때|
|HARD|✅|✅|✅|커밋을 완전히 버리고 이전 상태로 되돌릴 때|

### 커밋 되돌리기(Revert)

```bash
git revert HEAD
```

### 되돌리기(Revert) VS 초기화(Reset)

​
되돌리기(Revert) - 취소한 내용이라도 인덱스에 기록
​
초기화(Reset) - 취소한 내용을 알 수 없도록 인덱스 자체를 초기화
​

### 체리 픽(Cherry-Pick)

- 다른 브랜치에 잘못 추가한 커밋을 올바른 브랜치로 이동하려고 할 경우
- 다른 브랜치의 커밋을 현재 브랜치에도 추가하고 싶은 경우
​

```bash
git checkout [적용할 브랜치]
```

```bash
git cherry-pick [가져오려는 특정 커밋]
```

### Rebase

```bash
git rebase -i HEAD~[보여질 이전 커밋 항목 수]
```

​

- 이전 커밋 내용을 정리 할 때
- 커밋을 알기 쉽게 하나로 통합 할 때
- 누락된 변경사항을 추가할 때
​

#### 커밋 통합

​
여러 커밋을 하나로 통합합니다.

- 커밋 ‘a1a1a13’ 에 ‘a1a1a11’~’a1a1a12’ 통합

```bash
pick   a1a1a10 Edit-1
squash a1a1a11 Edit-2
squash a1a1a12 Edit-3
pick   a1a1a13 Edit-4
```

- 저장하고 종료
​

```bash
:wq
```

#### 커밋 수정

​
커밋 메시지를 수정합니다.
​

- 커밋 ‘a1a1a13’ 메시지 수정
​

```bash
pick   a1a1a10 Edit-1
pick   a1a1a11 Edit-2
pick   a1a1a12 Edit-3
reword a1a1a13 Edit-4
```

- 커밋 메시지 수정
​

```bash
Edit-4E 
```

- 저장하고 종료
​

```bash
:wq
```
