---
layout: default
title: Basic
description: "[Git] 기본 명령어"
parent: Git
grand_parent: Manual
nav_order: 2
---

# [Git] 기본 명령어

## clone 하기

1. `git init` :  git 이 직접적으로 관리하는 영역인 repository를 생성한다.

2. `git clone "git 주소"` :  프로젝트 전체를 복사해 온다.
3. `git checkout -b "branch 이름"` : branch를 만들면서 동시에 checkout 한다.

<br/>

## 브랜치 작업

`git branch -r` : remote 저장소에 있는 branch 이름 중 내가 알고 있는 목록을 보여준다.

`git pull "remote 저장소 이름" "branch 이름"` : 내가 가져오고 싶은 가지만 통째로 가져온다.

- 가져오는 명령어
`fetch` : 정보만 가져오고 내것을 합치지는 않음
`pull`  : fetch + merge

`git fetch github`
`git merge github/master`

<br/>

## push 하기

1. `git status` : 현재 상태를 확인한다
2. `git add .` : 모든 파일을 add한다. `.`이 아닌 `[파일]`만 add할 수 있다.
3. `git commit -m "message"` : commit message를 입력한다. 
4. `git push` : push한다.

<br/>

## 강제 pull / push 하기

`git fetch —all`

`git reset --hard origin`

`git pull origin master`

`git push -f`
