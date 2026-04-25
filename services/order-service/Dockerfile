FROM ghcr.io/astral-sh/uv:python3.14-bookworm-slim AS builder
WORKDIR /app
COPY pyproject.toml uv.lock ./
COPY services/order-service/pyproject.toml services/order-service/
RUN uv sync --package order-service --frozen --no-dev
COPY . .

FROM python:3.14-slim-bookworm
WORKDIR /app
COPY --from=builder --chown=app:app /app /app
ENV PATH="/app/.venv/bin:$PATH"

CMD ["fastapi", "run", "services/order-service/main.py", "--port", "8000", "--host", "0.0.0.0"]
