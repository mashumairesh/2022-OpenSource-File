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