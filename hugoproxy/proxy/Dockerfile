# Используем официальный образ Go как базовый
FROM golang:1.16-alpine as builder

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем исходники приложения в рабочую директорию
COPY . .
# Скачиваем все зависимости
RUN go mod init test && go mod tidy

# Собираем приложение
RUN go build -o main

# Начинаем новую стадию сборки на основе минимального образа
FROM alpine:latest



# Запускаем приложение
CMD ["/main"]
