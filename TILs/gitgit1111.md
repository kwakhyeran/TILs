## 0. 기본설정

아래의 설정은 이력작성자 (author) 를 설정하는것으로, 컴퓨터에서 최초에 한번만 설정하면 된다.

```bash


$ git config --global user.name kwakhyeran 으로 변경
$ git config --global user.email kwakli@naver.com <<으로 변경


```

## 1. 로컬 저장소 활용

### 1.저장소 초기화





* (master)는 현재 있는 브랜치 위피를 뜻하며, .git 폴더가 생성된다.
* 해당 폴더를 삭제하게 되면 모든 git과 관련된 이력이 삭제된다.



## 2. add

이력을 확정하기 위해서는 add명령어를 통하여 staging area에 stage 시킨다



```bash
$ git add .			#현재 디렉토리를 stage
$ git add README.md		#특정파일을 stage
$ git add images/		#특성 폴더를 stage
```



add를 한이후에는 항상 status 명령어를 통해 원하는 대로 되었는지 확인한다.

```bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   git.md
        new file:   images/44deb98d-1c50-4073-9bd7-2c2c28d65f9e.jpg
        new file:   images/f85afbc3-26f7-47a1-878e-fcbaa70a5354.jpg
        new file:   jjhouse.md

```

### 3. commit

git은 commit을 통해 이력을 남긴다. 커밋 시에는 항상 메시지를 통해 해당 이력의 정보를 나타내야한다.

```bash
$ git commit -m 'Init'
[master (root-commit) 943108b] Init
 4 files changed, 176 insertions(+)
 create mode 100644 git.md
 create mode 100644 images/44deb98d-1c50-4073-9bd7-2c2c28d65f9e.jpg
 create mode 100644 images/f85afbc3-26f7-47a1-878e-fcbaa70a5354.jpg
 create mode 100644 jjhouse.md

```

커밋목록은 아래의 명령어를 통해 확인가능하다.

```bash
$ git log
commit 943108b100a170d82d295e5173b91c8f6415969b (HEAD -> master)
Author: silverjjj <silver_jae@naver.com>
Date:   Thu Dec 5 16:52:33 2019 +0900

    Init
```



## 2. 원격저장소 (remote repository) 활용

> 원격저장소는 다양한 서비스를 통해 제공받을수있다.

> github, gitlab, bitbucket



### 1. 원격저장소 등록

```bash
$ git remote add origin http~
```

원격저장소(remote)를 origin이라는 이름으로 해당 url로 설정한다.

등록된 원격 저장소는 아래의 명령어로 확인할 수 있다.

등록은 한번만 실행하면 된다.

```bash
$ git remote -v
origin  https://github.com/silverjjj/TIL.git (fetch)
origin  https://github.com/silverjjj/TIL.git (push)

```



### 2. 원격 저장소 push

```bash
$ git push origin master
```

origin 원격 저장소에 push하기 되며, github에서 확인할수 있다.

이후 작업과정에서는 add-> commit 으로 이력을 남기고 push로 업로드 하면된다.