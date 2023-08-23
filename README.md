## 230823 ##

1. 로컬 저장소 생성<br>
`$ git init`<br>

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


1. 해당 레파지토리 내 저장소로 fork

(사용하던 git bash 에서 진행할때)
`$ clear` <- 작성되어 있던 내용 모두 삭제 (내용은 그대로 남아있음)
`$ cd ../` <- 한단계 돌아가는 명령어

(폴더에서 직접 프로그램 열어 시작할때)
`$ git clone https://fork해온 레파짓토리 URL` -> 로컬 저장소에 fork해온 온라인 저장소 저장
`$ cd 레파짓토리 이름/` <- 이름 일부 쓰고 Tab키 누르면 자동완성. 하면 들어감

﻿
3. forkEx1.txt 문서 생성후 fork 작업순서 작성
`$ touch forkEx1.txt`
생성된 파일에 내용 입력

4.포크된 내 온라인 저장소에 업로드
`$ git add .`
`$ git commit -m "남기는 메세지 작성"`
`$ git push -u origin main or master(원 주인설정에 따라)`



### Full request ###
#### 풀 리퀘스트(Full request)란? ####
* :포크로 가져온 레파짓토리를 내가 수정한 후 원작자에게 수정된 내용을 반영하도록 요청하는 과정

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