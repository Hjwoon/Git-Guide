### 협업 프로젝트
- <u>_먼저, 메인 레포 **fork** 해오기 !_</u>
<br><hr>
- 메인 레포(upstream)와 포크한 레포(origin)를 동기화하면서 작업하고 
- PR을 올리는 협업 방법

### 1. 기본 설정
먼저 메인 레포를 upstream으로 추가합니다. 이 과정은 한 번만 해주면 됩니다.
1. 터미널을 열고 포크한 레포의 디렉토리로 이동합니다.
```bash
cd path/to/your/forked-repo
```
2. 메인 레포를 upstream으로 추가합니다.
```bash
git remote add upstream https://github.com/원본-레포-소유자/원본-레포.git
```
### 2. upstream 레포의 최신 상태로 동기화
다음으로, upstream 레포의 변경 사항을 포크한 레포에 반영합니다.
1. upstream에서 최신 상태를 가져옵니다.
```bash
git fetch upstream
```
2. 로컬의 main 브랜치로 이동합니다.
```bash
git checkout main
```
3. upstream의 main 브랜치를 병합하여 동기화합니다.
```bash
git merge upstream/main
```
4. 변경 사항을 포크한 레포 (origin)의 main 브랜치에 푸시합니다.
```bash
git push origin main
```

### 3. 새로운 작업 브랜치 생성
새로운 작업을 위해 별도의 브랜치를 만들어 작업합니다.
1. 새로운 브랜치를 생성하고 이동합니다.
```bash
git checkout -b new-feature-branch
```
2. 새로운 브랜치에서 작업을 진행하고 커밋합니다.
```bash
# 파일 수정 후
git add .
git commit -m "Add new feature"
```

### 4. Pull Request (PR) 생성
작업이 완료되면 new-feature-branch를 origin으로 푸시하고, 메인 레포에 PR을 생성합니다.
1. 작업 브랜치를 origin으로 푸시합니다.
```bash
git push origin new-feature-branch
```
2. GitHub에 접속하여 포크한 레포지토리 페이지로 이동합니다.
   브라우저를 통해 GitHub에 접속하고 포크한 레포지토리 페이지로 이동합니다.
3. "Compare & pull request" 버튼을 클릭합니다.
   GitHub가 푸시된 새로운 브랜치를 감지하면 이 버튼을 보여줍니다. 이를 클릭하여 PR을 생성합니다.
4. PR 제목과 설명을 작성한 후 "Create pull request" 버튼을 클릭하여 PR을 생성합니다.

### 5. PR 병합 후 최신 상태 유지
PR이 메인 레포에 병합된 후에도 최신 상태를 유지하기 위해 위의 동기화 단계를 반복합니다.
1. main 브랜치로 이동하여 upstream의 최신 상태를 다시 가져옵니다.
```bash
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
```
2. 새로운 작업을 위한 브랜치를 생성하고 작업을 진행합니다.