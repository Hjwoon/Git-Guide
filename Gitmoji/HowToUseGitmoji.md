# Gitmoji 사용법 안내서

## 1. Gitmoji란 무엇인가?
Gitmoji는 커밋 메시지에 이모지를 사용하는 방식으로, 커밋의 목적을 시각적으로 표현하여 코드 변경 내용을 더 쉽게 이해할 수 있도록 도와줍니다. 각 이모지는 특정한 의미를 가지며, 이를 통해 커밋 히스토리를 직관적으로 파악할 수 있습니다.

## 2. Gitmoji 설치

### Node.js와 npm을 사용하여 Gitmoji CLI 설치
1. Node.js와 npm이 설치되어 있는지 확인합니다. 설치되어 있지 않다면 [Node.js 공식 사이트](https://nodejs.org/)에서 설치합니다.
2. Gitmoji CLI를 전역으로 설치합니다.
    ```bash
    npm install -g gitmoji-cli
    ```

## 3. Gitmoji 사용법

### Gitmoji 커밋
1. 터미널에서 다음 명령어를 실행하여 Gitmoji 커밋을 시작합니다.
    ```bash
    gitmoji -c
    ```
2. 프롬프트에 따라 커밋 메시지를 작성합니다.
    - **Choose a gitmoji**: 사용하려는 Gitmoji를 선택합니다.
    - **Enter the commit title**: 커밋 제목을 입력합니다.
    - **Enter the commit message**: 커밋 메시지를 입력합니다.
    - **Issue / PR reference**: 관련 이슈나 PR 번호를 입력합니다 (선택 사항).

### Gitmoji 사용 예시
```bash
gitmoji -c
```

```yaml
? Choose a gitmoji: 🎨  - Improving structure / format of the code.
? Enter the commit title: 코드 구조 개선
? Enter the commit message: 불필요한 파일 제거 및 코드 리팩토링
? Issue / PR reference: #42
```

## 4. 주요 Gitmoji 목록 및 의미

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


## 5. Gitmoji CLI 명령어
### 사용 가능한 Gitmoji 목록 보기
```bash
gitmoji -l
```

### Gitmoji CLI 업데이트
```bash
gitmoji -u
```

### Gitmoji 설정 초기화
```bash
gitmoji -i
```

<hr>

Gitmoji 공식 문서(https://gitmoji.dev/)