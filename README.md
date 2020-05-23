# Github의 기본적인 구성
```
          -스테이징->     --커밋-->     ---푸시--->
+-------------+--------------+------------+--------------+
| 작업 디렉토리 |    인덱스    |  로컬 저장소 |  원격 저장소   |
+-------------+--------------+------------+--------------+
                                      <-펫치-
```
|작업|이동|Git Bash / CMD / Powershell| 
|:-| - | - | -:| 
|스테이징|파일 -> 인덱스|git add ..|
|커밋|인덱스 -> 로컬저장소|git commit -m "commit message"|
|푸시|로컬저장소 -> 원격저장소|git push [Remote Repo] [Branch]|
|풀|원격저장소 -> 로컬저장소|git pull [Remote Repo] [Branch]|
|클론|원격저장소 -> 로컬저장소|git clone [Remote Repo]|

+ **작업 디렉토리 (Working Directory)**: 실제 파일이 위치한 디렉토리
+ **인덱스 (Index)**: 확정할 준비가 된 변경사항들이 모인 영역
+ **로컬 저장소 (Local Repository)**: 컴퓨터의 로컬 환경에 위치한 저장소
+ **원격 저장소 (Remote Repository)**: Github, Gitlab, BitBucket 등의 호스팅 서비스에서 호스팅된 저장소
+ **브랜치 (Branch)**: 복사된 원격 저장소로, 나중에 하나의 저장소로 병합될 수 있음 (기본적으로 master 브랜치가 생성됨)

#### 데이터 업로드
+ 스테이징 (Staging): 확정할 변경 사항들을 인덱스에 추가시키는 것
+ 커밋 (Commit): 인덱스의 변경 사항들을 확정시키는 것
+ 푸시 (Push): 확정된 변경사항들을 원격 저장소에 업로드함

#### 데이터 다운로드
+ 풀 (Pull): 최신 커밋을 모두 받아 자동으로 파일 병합 후 업데이트
+ 펫치 (Fetch): 최신 커밋을 모두 받아 업데이트
+ 클론 (Clone): 원격 저장소에서 모든 파일들을 가져옴

# Github 셋업 정리
### 컴퓨터 초기 셋업
1. Git 다운로드
2. Git Bash에서 다음 명령어 입력
```git config --global user.name GITHUB_ACCOUNT_NAME```
```git config --global user.email GITHUB_ACCOUNT_EMAIL```  

3. VSCode에서 다음 확장 프로그램 설치
+ GitLens
+ Git Project Manager (설정 필요)
+ Git History

### 프로젝트 초기 셋업
1. 깃허브에서 저장소 생성
2. VSCode 실행 -> 저장소가 될 폴더 열기 -> Source Control 탭으로 이동
3. VSCode의 터미널 혹은 Git Bash에서 git clone [저장소 URL] 명령 
(로컬 저장소를 만드는 작업, 이 과정에서 저장소 URL 별칭인 origin이 생성됨)

# 사용 정리
### Visual Studio 사용 (Source Control 탭)
+ 변경된 파일은 Changes의 파일 리스트에서 파일 옆의 +를 눌러 인덱스로 옮길 수 있음
+ Staged Changes의 파일 리스트에서 파일 옆의 -를 눌러 확정을 취소할 수도 있음
+ 확정된 변경과 커밋 메시지를 상단 바의 √ 버튼으로 커밋할 수 있음
+ 상단 바 메뉴의 Push로 변경이 확정된 파일들을 깃허브에 업로드할 수 있음
+ 다른 사람이 프로젝트를 업데이트했을 경우 Pull로 깃허브에서 로컬로 프로젝트를 업데이트할 수 있음 (git pull)
+ 업데이트된 파일들을 두 번 클릭하면 변경 내역을 볼 수 있음
+ Changes의 파일 리스트의 파일 옆 Discard Change 버튼으로 바뀐 내용을 취소할 수 있음

### 깃허브 웹사이트 셋업
1. 깃허브의 저장소에 index.html 업로드
2. 프로젝트의 Settings 탭 -> Github Pages 탭
3. Source에서 브랜치 선택
4. 완료

### 확장 기능
1. **GitLens**
+ 현재 라인에 깃허브 정보 추가 (최근 변경 시간/변경한 사용자 등)
+ 코드 렌즈 추가 (최근 변경 시간/변경한 사용자 등)
+ 상태표시줄의 프로젝트 정보 추가 
+ 현재 라인에 대한 커밋 설명 추가 (커밋 상세정보, 변경된 사항 등)
+ 저장소, 파일 히스토리, 라인 히스토리, 커밋 검색, 비교 등 사이드바 추가
2. **Git Project Manager** - Git 프로젝트 폴더를 VSCode 안에서 기존 창/새로운 창으로 열 수 있게 함
3. **Git History** - Git 로그를 읽고 그래프와 상세 정보로 정리하며, 프로젝트의 브랜치와 파일들을 보고 비교할 수 있게 함


#### 그 외
깃허브에서 자주 만나는 문제들: https://parksb.github.io/article/28.html
