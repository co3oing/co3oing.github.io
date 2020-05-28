---
layout: default
title: Undo-Push
parent: Git
grand_parent: Manual
nav_order: 1
---

# [Git] push 취소, rebase를 통한 Author 변경

## push 취소하기

1. `git checkout [branch]`
   push를 취소할 branch로 checkout한다.
2. `git reset --hard HEAD^` : 가장 최신의 commit id로 되돌린다.<br/>

   `git reset --hard [commit id]` : 특정 commit id로 되돌린다.
3. `git push --force` 변경된 사항을 적용한다.

## Git 저장소 commit의 Author 변경하기

1. `git rebase -i [commit id]`
   바꾸고 싶은 commit을 잡아준다.
2. `pick` → `edit`
   바꾸고 싶은 commit을 `edit`으로 변경해준 후 저장한다.
3. `git commit --amend --author="[name] <[email]>]"`
   [name]과 [email]을 입력해 준다.
4. `git rebase --contine`
   다음으로 계속 진행한다.
5. `git push -f`
   변경된 내용을 적용한다.
6. `git rebase --abort`
   취소하고 싶을 경우 해당 명령어를 입력해준다.
