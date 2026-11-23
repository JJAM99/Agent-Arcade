# 노트북 작업 안내

팀에서 작성한 `.ipynb` 파일은 `notebooks/`에 저장합니다. 이 폴더의 `.gitkeep`은 빈 폴더를 Git에 유지하기 위한 파일입니다.

파일명은 `github아이디_01_data_overview.ipynb`처럼 작성자와 목적을 드러내도록 정하면 구분하기 쉽습니다. 필요하면 팀에서 합의해 하위 폴더를 추가하세요.

기존 노트북을 그대로 넣어도 됩니다. 새 분석에 사용할 선택 사항인 공통 템플릿은 `templates/notebooks/analysis_template.ipynb`에, 작성 정보 양식은 `templates/notebooks/author_template.md`에 있습니다.

프로젝트 루트에서 JupyterLab을 실행합니다. 공통 템플릿은 상위 폴더에서 프로젝트 루트를 찾아 데이터 경로를 설정합니다. 원본 데이터는 `data/raw/`에서 읽고 결과는 `data/processed/` 또는 `reports/`에 저장합니다.

커밋 전에 커널을 재시작하고 필요한 셀을 순서대로 실행해 확인한 뒤, 출력 전체를 지우고 저장해주세요. 출력에는 데이터나 인증 정보가 남을 수 있습니다. 재사용할 함수는 `src/agent_arcade/`로 옮깁니다.
