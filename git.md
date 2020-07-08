# Git

> GIt 은 분산형버전관리시스템(DVCS) 중 하나이다.

## 0. Git 기초 설정

* window 환경에서는 `git for windows`로 검색하여 `git bash`를 설치한다. [다운로드 링크](https://gitforwindows.org/)

* 최초에 컴퓨터에서 git을 사용하는 경우 아래의 설정을 진행한다.

  ```bash
  $ git config --global user.email jangjisu@msu.edu
  $ git config --global user.name molo6379
  # 확인
  $ git config --global -l
  ```

  * 이메일주소를 설정할 때, github에 가입된 이메일로 설정을 해야 커밋 이력이 github에 기록된다.

## 1. Git을 통한 버전관리 기본 흐름

### 1.1. Git 저장소 초기화

> 특정 폴더를 gut 저장소로 활용하기 위해서 최초에 입력하는 명령어

```bash
$git init
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/
(master) $
```

* `.git` 폴더가 숨긴 폴더로 생성되며, git bash에서는 (master) 라고 표기된다.
* 반드시 git으로 활용되고 있는 폴더 아래에서 저장소를 선언하자.

### 1.2. add

> 커밋 대상 파일들을 추가한다.

```bash
$ git status
On branch master

No commits yet
# 트래킹 되지 않는 파일들
# => 새로 생성된 파일이고, git으로 관리 중이지 않은 파일
Untracked files:
    # git add 파일
    # 커밋이 될 것들을 포함시키기 위해서 위의 명령어를 써라!
  (use "git add <file>..." to include in what will be committed)
        markdown-images/
        markdown.md

nothing added to commit but untracked files present (use "git add" to track)

```

```bash
$ git add .
$ git status
On branch master

No commits yet
# 커밋될 변경사항들
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   markdown-images/123145-1594185216608.PNG
        new file:   markdown-images/123145.PNG
        new file:   markdown.md

```

* add 명령어는 아래와 같이 활용된다.

```bash
$ git add . # 현재 디렉토리 전부
$ git add git.md markdown.md # 특정 파일
$ git add markdown-images/ # 특정 디렉토리
```

### 1.3. commit

> 이력을 확정 짓는 명령어

```bash
$ git commit -m 'Init' # 커밋 메세지
[master (root-commit) a195741] Init
 3 files changed, 85 insertions(+)
 create mode 100644 markdown-images/123145-1594185216608.PNG
 create mode 100644 markdown-images/123145.PNG
 create mode 100644 markdown.md

$ git status
On branch master
nothing to commit, working tree clean

```

#### `log`

>커밋 내역들을 확인할 수 있는 명령어

```bash
$ git log
commit a195741de8f871924e35ecd39e83788ea135f16a (HEAD -> master)
Author: molo6379 <jangjisu@msu.edu>
Date:   Wed Jul 8 14:43:00 2020 +0900

    Init

# 최근 n개 이력(1개)
$ git log -1
Author: molo6379 <jangjisu@msu.edu>
Date:   Wed Jul 8 14:43:00 2020 +0900

    Init

# 간략한 표현
$ git log --oneline
a195741 (HEAD -> master) Init

# 최근 n개 이력을 간략하게
$ git log --oneline -1
a195741 (HEAD -> master) Init
```

### 2.1. 원격 저장소 등록

> git아! 원격저장소(remote)로 등록해줘(add) origin 이라는 이름으로 URL을!

```bash
$ git remote add origin 저장소url
```

* 저장소 확인

  ```bash
  $ git remote -v
  origin https://github.com/molo6379/TIL.git (fetch)
  origin https://github.com/molo6379/TIL.git (push)
  ```

* 저장소 삭제

  origin으로 지정된 저장소를 rm(remove)한다.

  ```bash
  $ git remote rm origin
  ```

### 2.2. push

origin으로 설정된 원격저장소의 master 브랜치로 push한다.

```bash
$ git push origin master
```





