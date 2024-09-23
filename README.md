# XR 메타버스 창작자 실전 취업캠프

## 실습 프로젝트 1 - SpaceShooter

- [프로젝트 소스 리포](https://github.com/IndieGameMaker/SeSAC_SpaceShooter.git)

## 실습 프로젝트 2 - 네트워크 대전 게임

### 패키지

- [Photon PUN2 (2.54 버전)](assets/Photon245.unitypackage)
- [Tank Model](assets/TankAsset.unitypackage)

### 구글 드라이브

- [구글 드라이브](https://drive.google.com/drive/folders/1imBGCULO0gFJ2y3_JZIF6VYOqE003hXW?usp=sharing)

## Git Flow 방법론

![](assets/git-flow-new.png)

## 유니티 프로젝트 생성 절차

### 팀장이 해야할 프로젝트 및 Git 초기 설정

1. Github에서 리포지토리 생성
     - README.md 생성은 선택 사항
     - .gitignore 생성 : Unity 탬플릿 선택

2. 유니티 프로젝트 생성
     - 적절한 프로젝트 폴더안에 유니티 프로젝트 생성

3. 터미널에서 깃 초기화
     - 프로젝트 폴더로 이동 (cd 명령)
     - 깃 초기화 (git init)

4. 리모트 리포와 연결
     - git remote add origin [원격 리포 주소]

5. 원격 리포에서 초기 데이터 다운로드
     - git pull origin master
     - .gitignore 파일이 로컬로 다운로드 됐는지 확인

6. git lfs 설정
     - git lfs install
     - curl [.gitattributes 파일 URL] > .gitattributes

7. lfs 설정 커밋 후 푸시
     - git add .gitattributes 
     - git commit -m "Git LFS 설정"
     - git push origin master

8. 유니티 초기 프로젝트 파일 커밋 후 푸시
     - git add .
     - git commit -m "Project 초기파일 추가"
     - git push origin master

9. GitHub에서 develop 브랜치 생성

#### 팀원의 프로젝트 클론

1. 리모트 리포지토리 클론
     - 터미널에서 프로젝트 경로로 이동
     - git clone --branch develop [리모트 리포지토리 URL]

2. 팀원 개인 브랜치 생성
     - git checkout -b dev/[영문이니셜_3자]

#### 팀장의 로컬 마스터 브랜치 삭제

1. 팀장의 개인 브랜치 생성
     - git checkout -b develop

2. 마스터 브랜치 삭제
     - git branch --delete master

3. 팀장 개인 브랜치 생성
     - git checkout -b dev/[영문이니셜_3자]
  

---


- 작업 시작하기 전 깃 작업

```shell
# 로컬 조장소가 develop 브랜치인지 확인
git branch

# 만약 develop 브랜치가 아닌경우 develop 브랜치로 체크아웃
git checkout develop

# 원격 저장소의 develop 브랜치에서 가져오기(Pull)
git pull origin develop

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 정상적으로 pull이 완료된 후 자신의 개발 브랜치로 체크아웃
git checkout dev/LJH

# 로컬 develop 저장소의 변경사항을 자신의 개발 브랜치로 Merge 한다.
git merge develop

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 정상적으로 병합이 완료된 후 작업을 진행한다.

```

- 작업 종료 후 깃 작업

```shell
# 자신의 개발 브랜치의 작업내용을 모두 커밋한다.
git add .
git commit -m "작업 내용"

# 로컬 develop 브랜치로 체크아웃한다.
git checkout develop

# 자신의 개발 브랜치의 내용을 로컬 develop 브랜치로 병합(merge) 한다.
git merge dev/LJH

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 충돌을 해결하거나 정상적으로 병합이 완료된 경우 원격 develop 브랜치로 push 한다.
git push origin develop

# 만약 원격 리포지토리에 변경 사항이 있을 경우 먼저 Pull 한 후 Push 한다.
```
