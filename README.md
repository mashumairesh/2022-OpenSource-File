# 2022-OpenSource-Fall
오픈소스 이해

## 리눅스 커맨드라인 기초
> 모르면 실습이 불가능한 기초 커맨드라인 3가지
1. pwd: print working directory
2. ls:  list
3. cd:  Change Directory

## Vim Editor

-HOW TO USE VIM-
  
```bash
vim <FileName.Extension> // <FileName.Extension> 파일을 vim 에디터로 열기
```

- 파일을 처음에 열면 명령모드로 진입
- 입력 하려면 입력모드로 진입해야 함
  - 키보드에서 I 및 Insert 입력
- 명령모드 진입은 키보드에서 ESC키 누름
  - 명령모드 커맨드
    - 저장하기 > :w Write
    - 나오기 > :q Quit
    - 저장하고 나오기 > :wq Write and Quit

### How to Solve Troubleshooting when creating swap files
#### 스왑파일이 생기는 경우
1. 두 응용프로그램에서 하나의 파일을 동시에 수정
2. 크래시 때문에 파일이 비 정상적으로 닫힌 경우

#### 해결방법
Recorvery Mode를 이용하여 수정중인 파일을 복구 뒤 Swap File을 삭제.
```bash
vim -r <FileName.Extension>
```

## git

> 대표적으로 쓰이는 버전 관리 시스템(Version Control System, VCS)

### git과 GitHub의 차이점
 - git은 버전 관리 시스템이다
 - GitHub는 git이라는 기술을 기반으로 만든 플렛폼이다
  - GitHub에서 만들었는데, GitHub를 마이크로소프트가 인수함

### 다양한 버전 관리 시스템
 - 이름 변경
  - 최종.hwp, 최종1.hwp, 최종22213.hwp
 - 자동저장 기능
 - git 이전의 버전 관리 시스템
  - SVN, CVS, Mercurial
 - 요즘엔 git이 거의 표준이 됨
 
 ## vim으로 git폴더 생성
  ### git init
   - git init으로 폴더를 깃 저장소로 만든다.
   - rm -rf .git으로 깃 저장소를 일반 저장소로 변경할 수 있다.
   
  ### 일반 디렉토리랑 저장소의 차이는?
   - .git의 존재 여부
   
   Flow...
   mkdir ~ -> cd ~~~ -> git init -> 파일 생성... -> git status -> git add <file> ... -> git commit -a -m "Explanation" -> git log(로그 확인)...
   
## Commit?
 ### "Commit 커밋"이란?
  - Commit은 독립된 버전을 나타내는 스냅샷(Snapshot)이다.
 ### 이러한 Commit을 언제 만들지?
  - 1. 커밋은 논리적 변경이 있을 때 만든다.
  - 2. 커밋은 가능하면 작을수록 좋다
  - 2.1 서비스의 장애가 발생했을시에 대응성을 위함.
  - 2.2 커밋이 커진다면 리뷰등에서 시간이 오래 걸리게 된다.
  

# 2022-10-06

## 스테이징 영역
- 커밋에 포함시킬 변경분만 올리는 영역
  - stage의 뜻 : 무대 ( 영역 )
- 스테이징 영역을 잘 활용해야 커밋을 잘 만들 수 있다.
- 스테이징 영역에 File을 Add하고 수정한 뒤 다시 Status를 확인할 경우?
  - 스테이징된 변경 사항이 따로 존재하고 그 이후에 수정한 사항이 변경 사항으로 남게 된다.

- Stage Command
  - git add <FileName>
    - 스테이징 영역에 추가
  - git restore --staged <fileName>
    - 스테이징 영역에서 내림

- 모든파일 올리기
  - git add . << 모든 파일을 지칭. ( 주의해서 사용할 것 )
  - 파일의 스테이징 자체를 막아주는 파일이 존제
    - git ignore

## Branch
  ### "What is Branch?"
  - Branch는 나뭇가지란 뜻으로 커밋 사이를 가볍게 이동할 수 있는 어떤 포인터 같은 것이다.
    - Git은 기본적으로 main 혹은 master라는 기둥 역활을 하는 브랜치가 1개 존재한다.
  - git branch <name> 해당 name에 맞는 branch가 생성된다.
  - git branch - 현재 존재하는 브랜치를 표기한다.

  - git switch <BranchName> BranchName의 브랜치로 브랜치를 변경한다.
  - git checkout 과 git switch는 거의 동일한 명령어이다.

  ### "Merge"
  - 이슈를 만든 뒤 이슈창에서 Create a branch를 눌러 브랜치를 만들고 작업한다.
  - 이후 마스터에서 git merge <합병할 branch의 이름>을 이용하여 현제 작업한 브렌치를 메인에 병합한다.
 
## 중간고사 내용 정리
  1. 기본적으로 알아야 할 커맨드라인 명령어
    - pwd, cd, ls : 약자
  2. vim사용법
    - 명령모드와 입력모드의 차이, 어떻게 각 모드로 전환할 수 있는지
    - 명령모드에서 저장하고 빠져나오는 방법
  3. 버전관리를 사용하는 이유
    - 3가지 적기
  4. git과 gitHub의 차이.
  5. 저장소와 일반 디렉터리의 차이
  6. Commit log를 보고 싶을때 치는 명령어
  7. 커밋은 언제 만드는가 : 논리적 변경이 있을때 만든다.
  8. Head의 정의 : 현제 체크아웃한 브렌치의 가장 최신 커밋을 가리키는 포인터...
     저장소 만들 때 쓰는 명령어 : git init...
  9. 현재 상태를 확인하는 명령어 (git status)
  10. 스테이징 영역이 왜 존재하는가? - 서술하여라.
  11. 원하는 파일을 스테이징 영역에 올릴 때 쓰는 명령어.
  12. 커밋 메시지가 "abc"인 커밋을 만들고 싶을 때 어떻게 하나?
      다양한 방법이 존재할 수 있다.
    - git commit -m "abc"
    - git commit 하고 엔터를 친 후 , abc를 입력한다...
  13. git ignore 파일의 역활 - 서술하여라.
  14. 브랜치는 언제 만드는가?
  