# Git, GitHub, Gitmoji 가이드

이 튜토리얼은 Git, GitHub, Gitmoji의 설치 및 기본 사용법을 정리하기 위함입니다.

## 목차
1. [소개](#소개)
2. [Git 설치 및 기본 명령어](#git-설치-및-기본-명령어)
3. [GitHub 설정 및 사용법](#github-설정-및-사용법)
4. [Gitmoji 사용법](#gitmoji-사용법)
5. [추가 자료](#추가-자료)

## 개념 요약
### Git이란?
Git은 파일의 변경 이력을 기록하여, 여러 사람이 동시에 작업할 때도 문제 없이 협업할 수 있게 해주는 도구입니다. 개발자는 Git을 사용해 언제든지 이전 상태로 돌아갈 수 있고, 서로의 작업이 충돌하지 않도록 관리할 수 있습니다.

### GitHub란?
GitHub는 Git을 기반으로 하는 웹사이트로, 코드 저장소를 호스팅하고 협업을 지원합니다. 여기서는 이슈 추적, 프로젝트 관리, 코드 리뷰 등을 통해 팀원들과 효율적으로 협력할 수 있습니다.
### Gitmoji란?
Gitmoji는 커밋 메시지에 이모지를 추가하여, 코드 변경의 목적을 쉽게 알아볼 수 있게 해주는 도구입니다. 예를 들어, 버그 수정에는 🐛, 새로운 기능 추가에는 ✨와 같은 이모지를 사용합니다.


## Git 설치 및 기본 명령어

### 설치
#### macOS
Homebrew를 사용하여 Git 설치:
```sh
brew install git
```

##### Windows

Git for Windows 웹사이트(https://gitforwindows.org/) 에서 설치 프로그램 다운로드 및 설치. 

##### Linux

배포판의 패키지 관리자를 사용하여 Git 설치:
```sh
sudo apt-get install git  # Ubuntu
sudo yum install git      # CentOS
```

##### 기본 명령어
저장소 초기화
```shell
git init
```

저장소 복제
```shell
git clone <repository-url>
```

파일 추가 및 커밋
```shell
git add <file-name>
git commit -m "커밋 메시지"
```
필자는 git commit -m 명령어 대신 gitmoji를 사용한다.
자세한 내용은 [Gitmoji 사용법](#gitmoji-사용법)에서 소개
```shell
gitmoji -`c`
```

브랜치 관리
```shell
git branch <branch-name>  # 브랜치 생성
git checkout <branch-name>  # 브랜치 이동
git merge <branch-name>  # 브랜치 병합
```

원격 저장소와의 동기화
```shell
git remote add origin <repository-url>
git push origin <branch-name>
```

## GitHub 사용법
### 1. GitHub 계정 생성
GitHub(https://github.com/) 에 접속하여 계정을 생성합니다.

### 2. 저장소 생성
1. GitHub 웹사이트에서 프로필 메뉴에서 "Your repositories"를 클릭합니다.
2. "New" 버튼을 클릭하여 새 저장소를 생성합니다.
3. 저장소 이름, 설명, 공개 여부 등을 설정하고 "Create repository"를 클릭합니다.

### 3. GitHub에 코드 푸시
1. 로컬 저장소에서 GitHub 저장소를 원격 저장소로 추가합니다.
```shell
git remote add origin <repository-url>
```

2. 변경 사항을 커밋하고 푸시합니다.
```shell
git add .
git commit -m "Initial commit"
git push origin main
```

### 4. 이슈 및 풀 리퀘스트 관리
<b>이슈 생성</b>
1. 저장소 페이지에서 "Issues" 탭을 클릭합니다.
2. "New issue" 버튼을 클릭하여 새로운 이슈를 생성합니다.
3. 제목과 내용을 작성하고 "Submit new issue"를 클릭합니다.

<b>풀 리퀘스트 생성</b>
1. 저장소 페이지에서 "Pull requests" 탭을 클릭합니다.
2. "New pull request" 버튼을 클릭하여 새로운 풀 리퀘스트를 생성합니다.
3. 변경 사항을 비교하고 "Create pull request"를 클릭합니다.

### 5. GitHub Actions
- CI/CD 파이프라인을 설정하기 위해 GitHub Actions를 사용합니다.
- .github/workflows 디렉토리에 워크플로우 파일을 추가하여 자동화 작업을 설정합니다.

```yaml
name: CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up Node.js
        uses: actions/setup-node@v1
        with:
          node-version: '14'
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
```

## Gitmoji 사용법
### 1. Gitmoji 설치
```shell
npm install -g gitmoji-cli
```

### 2. Gitmoji 사용
Gitmoji는 커밋 메시지에 이모지를 추가하여 커밋의 목적을 명확히 합니다.

<b>커밋할 때 Gitmoji 사용</b>
```shell
gitmoji -c
```
- 위 명령어를 실행하면 커밋 메시지 작성 시 이모지를 선택할 수 있는 인터페이스가 나타납니다.

#### Gitmoji 예시

| 이모지 | 코드                            | 설명                    |
|--------|-------------------------------|-----------------------|
| 🎨 | `:art:`                       | 코드의 구조 / 형식 개선        |
| ⚡️ | `:zap:`                       | 성능 향상                 |
| 🔥 | `:fire:`                      | 코드 / 파일 제거            |
| 🐛 | `:bug:`                       | 버그 수정                 |
| 🚑 | `:ambulance:`                 | 중요한 긴급 배포             |
| ✨ | `:sparkles:`                  | 새로운 기능 추가             |
| 📝 | `:memo:`                      | 문서 추가 / 수정            |
| ✏️ | `:pencil2:`                   | 오타 수정                 |
| 💄 | `:lipstick:`                  | UI 및 스타일 파일 추가 / 수정   |
| 🎉 | `:tada:`                      | 프로젝트 시작               |
| ✅ | `:white_check_mark:`          | 테스트 추가 / 수정           |
| 🔒 | `:lock:`                      | 보안 이슈 해결              |
| 🔖 | `:bookmark:`                  | 릴리즈 / 버전 태그           |
| 💚 | `:green_heart:`               | CI 빌드 수정              |
| 📌 | `:pushpin:`                   | 특정 버전 의존성 고정          |
| 👷 | `:construction_worker:`       | CI 빌드 시스템 추가 / 수정     |
| 📈 | `:chart_with_upwards_trend:`  | 분석, 추적 코드 추가 / 수정     |
| ♻️ | `:recycle:`                   | 코드 리팩토링               |
| ➕ | `:heavy_plus_sign:`           | 의존성 추가                |
| ➖ | `:heavy_minus_sign:`          | 의존성 제거                |
| 🔧 | `:wrench:`                    | 구성 파일 추가 / 수정         |
| 🔨 | `:hammer:`                    | 개발 스크립트 추가 / 수정       |
| 🌐 | `:globe_with_meridians:`      | 국제화, 현지화              |
| 💩 | `:poop:`                      | 개선해야 할 불량 코드          |
| ⏪ | `:rewind:`                    | 변경 내용 되돌리기            |
| 🔀 | `:twisted_rightwards_arrows:` | 브랜치 병합                |
| 📦 | `:package:`                   | 컴파일된 파일 / 패키지 추가 / 수정 |
| 👽 | `:alien:`                     | 외부 API 변경으로 인한 코드 수정  |
| 🚚 | `:truck:`                     | 리소스 이동 / 이름 변경        |
| 📄 | `:page_facing_up:`            | 라이센스 추가 / 수정          |
| 💡 | `:bulb:`                      | 주석 추가 / 수정            |
| 🍻 | `:beers:`                     | 술에 취해 쓴 코드            |
| 🗃️ | `:card_file_box:`             | 데이터베이스 관련 변경사항        |
| 🔊 | `:loud_sound:`                | 로그 추가 / 수정            |
| 🙈 | `:see_no_evil:`               | .gitignore 추가 / 수정    |
| ⚗️ | `:alembic:`                   | 실험적 기능 추가              |
| 🔍 | `:mag:`                       | 검색 관련 코드 추가 / 수정      |
| 🛂 | `:passport_control:`          | 권한 관련 코드 추가 / 수정      |
| 🩹 | `:adhesive_bandage:`          | 간단한 수정                |
| 🧐 | `:monocle_face:`              | 데이터 조사 / 검사            |
| 🚸 | `:children_crossing:`         | 사용자 경험 향상              |
| 🏗️ | `:building_construction:`     | 주요 구조 변경               |
| 📱 | `:iphone:`                    | 모바일 관련 코드 추가 / 수정    |
|  🔌 | `:electric_plug:`             | 리소스 연결                |
| 🏎️ | `:racing_car:`                | 성능 최적화                |
| 🧱 | `:bricks:`                    | 인프라 관련 작업              |
| 🧑‍💻 | `:technologist:`              | 개발자 경험 향상              |
| 🥚 | `:egg:`                       | 이스터에그 추가              |
| 🔒️ | `:closed_lock_with_key:`      | 인증 관련 코드 추가 / 수정      |
| 🚮 | `:wastebasket:`               | 사용되지 않는 코드 제거          |
| 🥅 | `:goal_net:`                  | 목표 달성                  |
| 💫 | `:dizzy:`                     | 애니메이션 추가 / 수정          |
| 🛒 | `:shopping_cart:`             | 비즈니스 로직 구현 / 수정       |
| 🧵 | `:thread:`                    | 멀티스레딩 관련 작업           |
| 🦺 | `:safety_vest:`               | 안전 관련 코드 추가 / 수정      |


### 추가 자료
Git Documentation(https://git-scm.com/doc)<br>
GitHub Guides(https://docs.github.com/ko)<br>
Gitmoji Website(https://gitmoji.dev/)

