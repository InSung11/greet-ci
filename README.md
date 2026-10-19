# greet-ci

Python 3.11 이상과 uv 0.8.14를 사용합니다. 저장소 루트에서 실행합니다.

```bash
uv sync --locked
uv run --locked python greet.py Hee
uv run --locked python greet.py
```

출력은 각각 `Hello, Hee!`, `Hello, world!`입니다.

```bash
uv run --locked pytest -q greet.py
uv run --locked black --check greet.py
uv run --locked flake8 greet.py
uv run --locked mypy greet.py
uv build
```

main 대상 push와 PR에서 테스트 4개, 품질 검사, 빌드를 실행합니다.
배포 파일은 CI의 `greet-dist` artifact에서 확인합니다.
