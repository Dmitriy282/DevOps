FROM python:3.11-slim AS builder
WORKDIR /app
COPY . /app
# Установка зависимостей для сборки документации
RUN pip install sphinx
# Сборка документации
RUN shpinx build
RUN sudo apt install git


# Второй этап: образ с Nginx, копирование документации
FROM nginx:latest
COPY --from=builder /app/site /usr/share/nginx/html