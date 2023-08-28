# GIT #

### 깃 사용자 정보 등록 ###

`git config --global user.name "xxx1234"`<br>
`git config --global user.email "xxx@naver.com"`<br>


### 로컬에 저장된 정보 삭제하는 방법 ###

`git config --list` <- 정보확인<br>
`git config --unset --global user.name`<br>
`git config --unset --global user.email`<br>


### git 상태 확인 방법 ###
​
`$ git log` <- 모든 커밋 이력 확인<br>
`$ git log --oneline` <- 모든 커밋 간단하게 이력 확인<br>
`$ git log --oneline --graph` <-이력을 그래프로 확인<br>
`$ git status` <- 현재 상태 확인<br>

### 디렉토리 명령어로 생성 ###

`$ mkdir 폴더명` -> 저장소를 git에서 생성할 수 있음.<br>

### 파일 명령어로 생성 ###

`$ touch 파일명` ->폴더에 따로 파일 생성하지 않아도 git에서 파일 명령어로 생성 가능<br>
파일명^파일명^파일명 파일명 사이 띄어쓰기 후 여러개 동시에 생성도 가능하다.


### 파일 깃에 등록 ###

`$ git add 파일명.확장자`( ex README.md)<br>
`$ git add .` ->폴더 안에 변화가 있는 모든 파일 등록. 등록되지 않은 파일이 한번에 등록되는 간편함이 있다. 보통 제일 많이 씀.<br>


### 메세지 작성과 함께 커밋 남기기 ###

`$ git commit -m "파일 설명"` <= 파일 설명은 구체적으로 작성해야 하며 메세지를 작성하지 않으면 커밋이 되지 않음<br>
`$ git commit -am "파일 설명"` <-add, commit 동시에 설정(두번째 '한번 등록된' 커밋부터 사용가능)<br>



### branch 만들기 ###

* branch -줄기, 가지. main에 새로운 브랜치 생성<br>


`$ git branch (이름)` <- 브랜치 생성 ex: git branch dev<br>
`$ git switch dev` <- dev 브랜치로 이동<br>
`$ git switch main` <- main 브랜치로 이동<br>
`$ git switch -` <- 바로 직전 브랜치로 이동. 브랜치가 너무 많으면 안먹힐때도 있음.<br>
`$ git switch -c (이름)` <- 브랜치 생성과 함께 새로운 브랜치로 이동<br>
​
`$ git branch --list` 브랜치 리스트 확인<br>
`$ git merge dev` <- 병합(합치고자)하는 브랜치로 넘어와서 명령어 입력<br>
ex) main에 dev를 합치고싶다. ->메인에서 해당 명령어 입력<br>
`$ git merge dev project` <- 한칸 띄워서 여러개를 같이 병합할 수 있음<br>
​
`$ git branch -d dev <-dev` 브랜치가 이미 원격(gitHub)에 푸쉬되고 병합 되었을때만 삭제<br>
`$ git branch -D dev <- dev` 브랜치 강제 삭제<br>
​

### 깃허브와 로컬 연결하기 ###

`$ git remote add origin https://github.com/Hanywyam/ex1.git` <-깃허브에 등록한 레파짓토리의 URL을 깃에 연결<br>
`$ git config --list` 로 제대로 등록되었는지 remote.origin.url~로 확인할 수 있음.<br>
`$ git push -u origin main`  <- 로컬과 온라인을 연결PUSH. 완료되면 깃허브에서 확인가능.<br>
`$ git push` <- 브랜치 없고 메인만 있을때만 push로 간단하게 업로드 가능.<br>

​

### 깃허브와 로컬 연결 끊기 ###

깃허브: 레파짓토리에 셋팅에서 맨 하단 [Delete this repository]클릭해서 삭제<br>

로컬 저장소에 들어가서
`$ git remote rm origin` <- 깃허브 연결 끊기(삭제)<br>
`$ git config --list` 하면 remote로 시작하는 내용이 없는걸 확인할 수 있음.<br>

​로컬은 삭제하고 싶을 때 그냥 지우면 된다. -> 휴지통~ <br>

​

### 마크다운 문서 작성 법 ###

`README.me` <-마크다운 문서<br>

# 큰제목 #

## 부제목 ##

__굵은글씨__ (언더바 두개)

마크다운 문서는 깃허브에 레파짓토리의 대문으로 활용함<br>

마크다운 참고 : https://github.com/tchapi/markdown-cheatsheet <br>
​



### GIT 기본 SETING ###

1. 로컬 저장소 생성<br>
`$ git init` ->해당 폴더에 ".git" 폴더 생성되면 git main 저장소 생성 성공<br>

2. README.md 파일 생성<br>
`$ touch README.md`<br>
or 메모장에 README.md 확장자로 해서 저장<br>
`$ git add .`<br>
`$ git commit -m "남기는 메세지 작성"` <-최초 커밋 등록<br>
`$ git log` <- 잘 기록됐는지 확인<br>
`$ git commit -am "남기는 메세지 작성"` <- 등록 후에는 파일추가와 커밋 함께 등록 가능<br>

3. 온라인 저장소 생성<br>
gitHub에서 new 버튼으로 레파짓토리 이름 작성 후 생성<br>
`$ git remote add origin https://github.com/사용자명/레파짓이름.git`<br>

4. README.md 파일 온라인 저장소에 업로드<br>
`$ git push -u origin main`<br>

### github에서 내려 받기 ###
`$ git pull origin main`

### clone과 pull의 특징 ###

1. clone : 로컬에 저장소가 없는 경우. 저장소 자체를 복사.
2. pull : 로컬에 연결된 저장소가 있는 경우. 저장소 안에 있는 파일을 내려받기.

### 충돌(CONFLICT)시 해결 방법 ###
__충돌 이유__
:하나의 문서가 온라인과 로컬에서 각각 수정이 일어났기 때문<br>

__해결 방법__
1. 온라인 저장소 README.md 파일 수정<br>
2. 로컬 저장소 README.md 내용 추가하여 수정 파일 커밋<br>
`$ git commit -am "메세지 작성"`<br>
3. 온라인 업로드 `$ git push` -> 충돌발생<br>
4. 온라인 저장소 파일 내려받기<br>
`$ git pull origin main`<br>
5. 수정한 README.md 파일 open >로컬과 온라인에서 수정된 내용 정리<br>
6. 수정 내용 커밋<br>
`$ git commit -am "충돌 내용 수정"`<br>
7. 온라인 저장소로 push<br>
`$ git push -u origin main`<br>
8. 로컬과 온라인 모두 동일한 내용으로 업데이트<br>

### fork 연습 ###


1. 해당 레파지토리 내 저장소로 fork<br>
2. 로컬 저장소로 복사<br>
* 사용하던 git bash 에서 진행할때<br>
`$ clear` <- 작성되어 있던 내용 모두 삭제 (내용은 그대로 남아있음)<br>
`$ cd ../` <- 한단계 돌아가는 명령어<br>
<br>

* 폴더에서 직접 프로그램 열어 시작할때<br>
`$ git clone https://fork해온 레파짓토리 URL` -> 로컬 저장소에 fork해온 온라인 저장소 저장<br>
`$ cd 레파짓토리 이름/` <- 이름 일부 쓰고 Tab키 누르면 자동완성. 하면 들어감<br>

﻿
3. forkEx1.txt 문서 생성후 fork 작업순서 작성<br>
`$ touch forkEx1.txt`<br>
생성된 파일에 내용 입력<br>

4.포크된 내 온라인 저장소에 업로드<br>
`$ git add .`<br>
`$ git commit -m "남기는 메세지 작성"`<br>
`$ git push -u origin main or master(원 주인설정에 따라)`<br>



### Full request ###
#### 풀 리퀘스트(Full request)란? ####
* 포크로 가져온 레파짓토리를 내가 수정한 후 원작자에게 수정된 내용을 반영하도록 요청하는 과정

#### 풀 리퀘스트 하는 방법 ####
1. 포크해온 내 github의 저장소에서 파일을 로컬로 복제
`$ git clone ﻿https://~fork해온 내 온라인 저장소에서 URL 복사/붙여넣기`
2. 복제된 파일에 들어가 변경사항 수정 후 커밋하여 온라인으로 push -> 포크해온 내 저장소 내용 수정됨.
3. 상단 `Pull requests` 클릭 > `New pull request` 버튼 클릭 > `create pull request` 버튼 클릭
4. 보내는 커밋 메세지 작성하여 `create pull request` 버튼 클릭
5. 전송되면 원작자의 repository pull requests 탭에서 확인 가능

#### 내가 받은 풀 리퀘스트 확인하는 방법 ####
1. 상단 `Pull requests` 클릭
2. 받은 리퀘스트 내용 검토
3. 첫 승인은 바로 가능 두번째부터 충돌이 생기며 수정해서 등록이 가능
4. 충돌 수정하여 `Merge pull request` 버튼 클릭 후 승인
