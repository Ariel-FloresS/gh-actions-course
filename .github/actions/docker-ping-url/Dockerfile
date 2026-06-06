FROM python:3.13-slim
# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/
#copy everything into /app
COPY . /app
# avoid instaling dev dependencies
ENV UV_NO_DEV=1

#copy the image python version (python:3.13-slim) into uv
ENV UV_PROJECT_ENVIRONMENT=/usr/local

WORKDIR /app
#install all the dependencies
RUN uv sync --locked

CMD ["python", "/app/main.py"]