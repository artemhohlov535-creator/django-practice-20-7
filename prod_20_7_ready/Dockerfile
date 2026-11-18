FROM python:3.12-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    POETRY_VIRTUALENVS_CREATE=false \
    POETRY_NO_INTERACTION=1

WORKDIR /app

RUN pip install --no-cache-dir poetry==2.2.1

COPY pyproject.toml ./
RUN poetry install --no-root

COPY mysite ./mysite
COPY shopapp-fixtures.json ./shopapp-fixtures.json
COPY README.md ./README.md

EXPOSE 8000

CMD ["python", "mysite/manage.py", "runserver", "0.0.0.0:8000"]
