# Git 기초 문법

> 분산 버전 관리시스템(DVCS)

## 준비 사항

* git bash(윈도우 사용하는 경우 필요)

## 기본 문법

### 0. git 저장소 생성

```bash
$ git init
# 비어있는 git 저장소(repository) 초기화했다..
# test 폴더에(절대경로) .git 폴더에..
Initialized empty Git repository in C:/Users/hoe/Desktop/test/.git/
(master) $
```

* 폴더에 git 저장소를 초기화하면, 
  * `.git` 폴더가 생성되고
  * bash에는 `(master)`라고 표기 된다.
* 주의사항!
  * git 저장소 내에 git 저장소를 만들지 말라.
    * `git init` 명령어 입력할 때, `master`가 보이면 절대 입력하지 말것!#

### 1. `add`

```bash
$ git add {디렉토리}
$ git add .	# 현재 디렉토리 (하위 디렉토리 포함)
$ git add a.txt # 특정 파일
$ git add myfolder/ # 특정 폴더
```

* `working directory` 상태의 파일을 `staging area` 상태로 변경
* Commit을 위한 파일들을 추가하는 명령어

### 예시

```bash
$ touch a.txt	# 파일을 만든다 => 코드 작업을 했다.
$ git status
On branch master

No commits yet
# Untracked files : Tracking X 파일들
# git으로 관리된 적 없는 파일들.. 예) 파일 생성
Untracked files:
# git add 명령어를 사용해라
# commit이 될 곳에 포함시키기위해서.. => staging area..
  (use "git add <file>..." to include in what will be committed)
        a.txt # <-- 빨간색...
# 총평
# nothing added to commit : 커밋할 것이 없음 (SA(staging area) X)
# untracked files present : WD(working directory) O
nothing added to commit but untracked files present (use "git add" to track)
```

```
$ git status
On branch master

No commits yet
# 커밋될 변경사항들 : staging area
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt
		# 새로운 파일
```

### 2. `commit`

```
$ git commit -m '{커밋메세지}'
[master (root-commit) e6eeb11] a.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt
```

* 커밋을 통해 하나의 버전으로 기록된다.
* 커밋 메세지는 현재 변경사항들을 잘 나타낼 수 있도록 작성하자.
* 커밋은 고유한 아이디인 해시값을 가진다.
  * SHA-1 알고리즘에 의해 생성
* 커밋 목록은 `git log` 명령어를 통해 확인할 수 있다.

### 3. `log`

```bash
$ git log
commit e6eeb11229f0172424d41c5413b5f406d0e99a65	# 해시값 (HEAD -> master)
Author: qweruiop <superinssa@gmail.com>
Date:   Thu Jun 3 15:34:47 2021 +0900

	Add a.txt

$ git log --oneline # 한줄로
e6eeb11 (HEAD -> master)

$ git log -2 # 2개
$ git log --oneline -1 # 1개를 한줄로
```

### 4. status

* working directory, staging area

```bash
$ git status
On branch master
nothing to commit, working tree clean
```







