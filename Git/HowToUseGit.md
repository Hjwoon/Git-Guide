# Git 사용법 안내서

## 1. Git이란 무엇인가?
Git은 분산 버전 관리 시스템(DVCS)으로, 소프트웨어 개발 중 코드의 변화를 기록하고 협업을 가능하게 합니다. Linus Torvalds가 리눅스 커널 개발을 위해 만든 시스템으로, 현재는 대부분의 소프트웨어 프로젝트에서 사용되고 있습니다.

![KakaoTalk_20240727_163448038.png](..%2Fimages%2FKakaoTalk_20240727_163448038.png)

## 2. Git 설치하기
Git을 사용하기 위해서는 먼저 Git을 설치해야 합니다.

### Windows
1. [Git 공식 사이트](https://git-scm.com/)에서 Windows 설치 파일을 다운로드합니다.
2. 다운로드한 설치 파일을 실행하고 설치 마법사의 지시에 따릅니다.

### macOS
1. 터미널을 열고 다음 명령어를 실행하여 Homebrew를 통해 Git을 설치합니다.
    ```bash
    brew install git
    ```

### Linux
1. 패키지 관리자를 사용하여 Git을 설치합니다.
    ```bash
    sudo apt-get install git  # Debian/Ubuntu 계열
    sudo yum install git      # RHEL/CentOS 계열
    ```

## 3. Git 기본 설정
Git 설치 후, 사용자 정보를 설정합니다.
```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

## 4. Git 기본 명령어
### 저장소 초기화
새로운 Git 저장소를 초기화합니다.
```bash
git init
```

### 기존 저장소 클론
원격 저장소를 로컬에 클론합니다.
```bash
git clone <repository_url>
```

### 상태 확인
작업 디렉토리의 상태를 확인합니다.
```bash
git status
```

### 파일 추가
파일을 스테이징 영역에 추가합니다.
```bash
git add <file_name>
git add .  # 모든 변경 사항 추가
```

### 커밋
스테이징된 파일을 커밋합니다.
```bash
git commit -m "커밋 메시지"
```
깃모지 사용
```bash
gitmoji -`c`
```

### 로그 확인
커밋 로그를 확인합니다.
```bash
git log
```

### 원격 저장소 추가
원격 저장소를 추가합니다.
```bash
git remote add origin <repository_url>
```

### 원격 저장소로 푸시
로컬 커밋을 원격 저장소로 푸시합니다.
```bash
git push origin <branch_name>
```

### 원격 저장소에서 풀
원격 저장소의 변경 사항을 로컬로 가져옵니다.
```bash
git pull origin <branch_name>
```


## 5. 브랜치 관리
### 브랜치 생성
새로운 브랜치를 생성합니다.
```bash
git branch <branch_name>
```

### 브랜치 전환
다른 브랜치로 전환합니다.
```bash
git checkout <branch_name>
```

### 브랜치 생성 및 전환
새로운 브랜치를 생성하고 전환합니다.
```bash
git checkout -b <branch_name>
```

### 브랜치 삭제
브랜치를 삭제합니다.
```bash
git branch -d <branch_name>
```

## 6. 병합 및 충돌 해결
### 브랜치 병합
다른 브랜치를 현재 브랜치에 병합합니다.
```bash
git merge <branch_name>
```

### 충돌 해결
충돌이 발생한 파일을 수동으로 편집하고 변경 사항을 추가한 후 커밋합니다.
```bash
git add <conflicted_file>
git commit -m "충돌 해결 메시지"
```

## 7. 원격 저장소와의 상호작용
### 원격 저장소 확인
현재 설정된 원격 저장소를 확인합니다.
```bash
git remote -v
```

### 원격 저장소 변경
원격 저장소 URL을 변경합니다.
```bash
git remote set-url origin <new_repository_url>
```

## 8. 기타 유용한 명령어
### 파일 삭제
Git에서 파일을 삭제하고 커밋합니다.
```bash
git rm <file_name>
git commit -m "파일 삭제 메시지"
```

### 커밋 수정
마지막 커밋 메시지를 수정합니다.
```bash
git commit --amend -m "새 커밋 메시지"
```

### 파일 무시
Git이 특정 파일 또는 디렉토리를 무시하도록 설정합니다. .gitignore 파일을 생성하여 무시할 패턴을 작성합니다.
```bash
# .gitignore 파일 예시
*.log
node_modules/
dist/
```

## 9. Git 워크플로우
### 기본 워크플로우
1. 변경 사항 작업
2. 변경 사항 스테이징 (git add)
3. 변경 사항 커밋 (git commit)
4. 원격 저장소로 푸시 (git push)

### 협업 워크플로우
1. 원격 저장소의 최신 변경 사항 가져오기 (git pull)
2. 새로운 브랜치 생성 및 전환 (git checkout -b <branch_name>)
3. 변경 사항 작업 및 커밋
4. 브랜치 병합 (git merge)
5. 원격 저장소로 푸시

## 10. 협업 시 주의할 점

### 병합(Merge) 시 주의할 점

1. **충돌 방지**: 병합하기 전에 항상 최신 변경 사항을 반영하세요. 병합할 브랜치에서 다음 명령어를 사용하여 최신 변경 사항을 가져옵니다.
    ```bash
    git pull origin <branch_name>
    ```

2. **충돌 해결**: 충돌이 발생하면, Git이 표시하는 충돌 파일을 열어 수동으로 수정합니다. 수정 후, 변경 사항을 추가하고 커밋합니다.
    ```bash
    git add <conflicted_file>
    git commit -m "충돌 해결 메시지"
    ```

3. **커밋 메시지**: 명확한 커밋 메시지를 작성하여 변경 사항의 목적과 내용을 설명합니다.

4. **리뷰 요청**: 병합 전에는 동료 개발자에게 코드 리뷰를 요청합니다. 이는 코드 품질을 높이고 버그를 줄이는 데 도움이 됩니다.

### Pull Request(PR) 규칙

1. **작은 단위로 PR 작성**: 큰 PR보다는 작은 단위의 PR을 작성하여 코드 리뷰가 쉽도록 합니다.

2. **명확한 제목과 설명**: PR 제목과 설명을 명확하게 작성합니다. 변경 사항의 목적, 주요 변경 내용, 테스트 방법 등을 포함합니다.

3. **자동화된 테스트**: 가능하면 자동화된 테스트를 포함하여 변경 사항이 기존 기능을 망가뜨리지 않는지 확인합니다.

4. **리뷰어 지정**: 코드 리뷰어를 지정하여 PR을 검토하고 피드백을 받습니다.

5. **기능 브랜치 사용**: 새로운 기능이나 버그 수정은 항상 별도의 브랜치에서 작업하고, 이 브랜치를 PR을 통해 메인 브랜치에 병합합니다.

6. **리뷰 피드백 반영**: 리뷰어의 피드백을 신속하게 반영하고, 필요 시 추가 커밋을 작성하여 PR을 업데이트합니다.

7. **최신 상태 유지**: PR을 진행하는 동안 메인 브랜치의 변경 사항을 정기적으로 반영하여 PR 브랜치를 최신 상태로 유지합니다.
    ```bash
    git pull origin main
    ```

8. **테스트 완료**: 모든 변경 사항은 PR 병합 전에 충분히 테스트하여 문제를 방지합니다.
