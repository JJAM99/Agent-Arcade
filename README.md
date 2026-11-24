# Agent Arcade

강화학습 몬스터와 싸우는 2D 로그라이크 던전 RPG

## 게임 소개

- 플레이어가 직접 조작해 던전을 탐험하고 스테이지를 클리어한다
- 스테이지가 바뀔 때마다 시대 배경이 바뀐다 (예: 중세 → 우주)
- 마지막 보스는 플레이어의 플레이를 모방한 **분신 보스**

## 핵심 목표

- 규칙 기반 보스, 모방 분신(지도학습), 강화학습 분신을 비교한다
- 분신이 플레이어를 닮아가며 강해지는 과정을 시각화한다

## 구현 순서

1. 규칙 기반 몬스터·보스와 기본 전투
2. 플레이 기록으로 모방 모델 학습
3. 강화학습으로 분신 강화
4. 성능 비교와 시각화

## 확장 아이디어

- 파티 협동 AI, 소환수 키우기

## 프로젝트 정보

| 항목 | 내용 |
| --- | --- |
| 기술 스택 | 팀에서 작성 예정 |
| 팀원 및 역할 | 팀에서 작성 예정 |

이 저장소는 팀원별 Jupyter 노트북, 데이터, 공용 Python 코드, 실험 결과를 정리할 기본 구조를 제공합니다.

## 시작하기

```bash
git clone https://github.com/JJAM99/Agent-Arcade.git
cd Agent-Arcade
```

Python 3 환경에서 프로젝트 루트를 기준으로 실행합니다. 팀 공통 Python 버전과 패키지 버전은 아직 확정하지 않았습니다.

```bash
python -m venv .venv
```

가상 환경을 활성화합니다.

```bash
# macOS / Linux / WSL
source .venv/bin/activate
```

```powershell
# Windows PowerShell
.venv\Scripts\Activate.ps1
```

의존성을 설치하고 JupyterLab을 실행합니다.

```bash
python -m pip install -r requirements.txt
python -m jupyterlab
```

팀에서 작성한 `.ipynb` 파일은 `notebooks/`에 넣어 작업하세요. 새 분석용 템플릿이 필요하면 `templates/notebooks/analysis_template.ipynb`를 복사해 사용할 수 있습니다. 자세한 규칙은 [노트북 안내](docs/NOTEBOOKS.md)를 참고합니다.

실제 데이터는 별도로 준비해 `data/raw/`에 넣습니다. 데이터 출처와 공유 위치는 `data/metadata/datasets.csv`에 기록하세요. [데이터 안내](data/README.md)에 폴더별 용도와 Git 포함 범위가 있습니다.

현재 템플릿과 작업 폴더만 제공하며, 애플리케이션 실행 코드와 자동 테스트·빌드 명령은 아직 없습니다. 필요한 환경 변수도 정해지지 않았으며 `.env.example`에 추후 추가합니다.

실제 비밀번호, API 키, 토큰이 들어 있는 `.env` 파일은 커밋하지 않습니다. 환경 변수 예시 파일에는 가짜 값만 사용해주세요.

## 협업 방법

1. 이슈 템플릿으로 할 일을 등록하고 담당자를 정합니다.
2. 최신 `main`에서 작업 브랜치를 만듭니다. 예: `feat/12-login`.
3. 작업과 검증을 마친 뒤 `main`을 대상으로 Pull Request를 엽니다.
4. 팀원의 리뷰를 받고, 대화와 충돌을 해결한 뒤 병합합니다.

자세한 규칙은 [기여 가이드](CONTRIBUTING.md), 상호 존중에 대한 약속은 [행동 규칙](CODE_OF_CONDUCT.md)을 참고해주세요.

## 저장소 구성

```text
.github/
  ISSUE_TEMPLATE/          # 버그 및 기능 제안 양식
  pull_request_template.md
notebooks/                # 팀에서 작성한 .ipynb 파일
templates/notebooks/      # 선택해서 쓰는 노트북 템플릿 및 작성 양식
data/
  raw/                    # 원본 데이터 (Git 제외)
  external/               # 외부 참고 데이터 (Git 제외)
  interim/                # 중간 처리 결과 (Git 제외)
  processed/              # 최종 가공 데이터 (Git 제외)
  samples/                # 공유 가능한 작은 예시 데이터
  metadata/               # 데이터 출처 및 재현 방법
src/agent_arcade/         # 재사용하는 공용 Python 코드
configs/                  # 실험 설정 예시
scripts/                  # 수집·전처리·학습 실행 스크립트
tests/                    # 향후 공용 코드 테스트
models/                   # 모델 산출물 (Git 제외)
reports/
  figures/                # 공유 가능한 결과 그림
  experiment_template.md  # 실험 기록 양식
docs/
  NOTEBOOKS.md             # 노트북 작업 안내
  TEAM_SETUP.md            # GitHub 관리자 설정 체크리스트
requirements.txt          # 노트북 기본 도구
.env.example              # 환경 변수 작성 안내
.editorconfig             # 공통 편집 규칙
.gitattributes            # 줄바꿈 정규화
.gitignore                # 로컬 파일 및 비밀 정보 제외
CODE_OF_CONDUCT.md
CONTRIBUTING.md
README.md
```

## 팀 설정

저장소 생성 후 관리자가 확인할 항목은 [팀 설정 체크리스트](docs/TEAM_SETUP.md)에 정리했습니다. 브랜치 보호와 리뷰 필수 설정은 GitHub에서 별도로 적용해야 합니다.

## 라이선스

라이선스는 아직 정하지 않았습니다. 외부 공개 및 재사용 정책을 팀에서 합의한 뒤 `LICENSE` 파일과 이 항목을 업데이트해주세요.
