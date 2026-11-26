# Agent Arcade

플레이어가 던전을 탐험하고 자신의 전투 스타일을 학습한 분신 보스와 싸우는 2D 로그라이크 RPG입니다. 스테이지가 바뀌면 시대 배경도 바뀝니다.

## 보스 AI

| 방식 | 행동 결정 |
| --- | --- |
| 규칙 기반 | 거리, 체력 등 전투 상태에 따라 미리 작성한 규칙으로 행동합니다. 다른 방식의 비교 기준입니다. |
| 지도학습 | 플레이 기록에서 전투 상태와 플레이어 행동의 짝을 학습해 플레이어를 모방합니다. |
| 강화학습 | 전투를 반복하며 보상에 따라 분신의 행동 정책을 개선합니다. |

같은 전투 규칙과 초기 조건에서 승률, 전투 시간, 플레이어와의 행동 유사도를 비교합니다.

## 현재 상태와 실행

브라우저에서 [이동 프로토타입](notebooks/index.html)을 열고 `W`, `A`, `S`, `D`로 움직일 수 있습니다. 세 보스 방식의 구현과 공용 전투 환경은 개발 계획에 포함되어 있습니다.

노트북 실험에는 Python 3.12 이상과 `uv`를 사용합니다. 저장소 루트에서 다음을 실행합니다.

```bash
git clone https://github.com/JJAM99/Agent-Arcade.git
cd Agent-Arcade
uv sync --locked
uv run jupyter lab
```

## 개발 순서

1. 기본 전투와 규칙 기반 몬스터·보스를 구현합니다.
2. 플레이 기록을 수집하고 지도학습으로 분신을 훈련합니다.
3. 전투 환경과 보상을 정의하고 강화학습으로 분신을 훈련합니다.
4. 세 보스를 같은 조건에서 평가하고 결과를 시각화합니다.

## 저장소 구성

| 경로 | 용도 |
| --- | --- |
| [`notebooks/`](notebooks/) | HTML 프로토타입과 팀 실험 노트북 |
| [`src/agent_arcade/`](src/README.md) | 공용 Python 코드 |
| [`data/`](data/README.md) | 플레이 기록과 학습·평가 데이터 |
| [`configs/`](configs/README.md), [`scripts/`](scripts/README.md) | 실험 설정과 실행 스크립트 |
| [`models/`](models/README.md), [`reports/`](reports/README.md) | 학습 산출물과 평가 기록 |
| [`tests/`](tests/README.md) | 공용 코드와 전투 환경 검증 |

## 협업

작업 브랜치에서 변경하고 `main`을 대상으로 PR을 엽니다. [기여 가이드](CONTRIBUTING.md), [팀 행동 규칙](CODE_OF_CONDUCT.md), [팀 설정](docs/TEAM_SETUP.md)을 참고하세요.

- [노트북 작업 안내](docs/NOTEBOOKS.md)
- [Claude 작업 가이드](CLAUDE.md)
- [Codex 작업 가이드](CODEX.md)

라이선스는 팀에서 결정할 예정입니다.
