FROM python:3.9.2-slim-buster

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt-get update \
    && apt-get -y install netcat gcc \
    && apt-get clean

RUN pip install --upgrade pip
RUN pip install poetry
COPY ./poetry.lock .
COPY ./pyproject.toml .
RUN poetry config virtualenvs.create false \
    && poetry install

COPY . .
