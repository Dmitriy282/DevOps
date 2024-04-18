FROM python:3.11 AS builder
WORKDIR /app
COPY . /app
# Установка зависимостей для сборки документации
RUN pip install mkdocs
# Сборка документации
RUN mkdocs build

# Второй этап: образ с Nginx, копирование документации
FROM nginx:latest
COPY --from=builder /app/site /usr/share/nginx/html