FROM python:3.13
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin
WORKDIR /code
COPY pyproject.toml .python-version uv.lock ./


COPY src/ ./src/

RUN uv sync --locked

ENTRYPOINT ["uv", "run", "python", "-m", "pipeline.pipeline"]