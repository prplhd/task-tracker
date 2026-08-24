# Проект “[Планировщик задач](https://zhukovsd.github.io/java-backend-learning-course/projects/task-tracker/)”

Микросервисное веб-приложение для управления задачами.

Пользователь может зарегистрироваться, авторизоваться, создавать, редактировать, завершать и удалять задачи. После регистрации отправляется приветственное письмо, а раз в сутки пользователь получает сгенерированный LLM отчёт по выполненным и оставшимся задачам.

## Стек

- Java 21
- Spring Boot
- Spring Security + JWT
- Spring Data JPA
- Liquibase
- PostgreSQL
- Apache Kafka
- Spring Kafka
- Spring Scheduler
- Spring Mail
- GigaChat API
- Docker / Docker Compose
- Nginx
- HTML / CSS / JavaScript
- GitHub Actions

## Репозитории

- [Общий репозиторий / Docker Compose](https://github.com/prplhd/task-tracker)
- [Backend](https://github.com/prplhd/task-tracker-backend)
- [Frontend](https://github.com/prplhd/tack-tracker-frontend)
- [Scheduler](https://github.com/prplhd/task-tracker-scheduler)
- [Email Sender](https://github.com/prplhd/task-tracker-email-sender)
- [Summarization](https://github.com/prplhd/task-tracker-summarization)

## Запуск через Docker Compose

Клонировать основной репозиторий:

```bash
git clone https://github.com/prplhd/task-tracker.git
cd task-tracker
```

Создать файл `.env` по примеру `.env.example` и заполнить необходимые переменные окружения:

```bash
cp .env.example .env
```

Запустить production-стек:

```bash
docker compose -f docker-compose.prod.yml up -d
```

Docker Compose запустит PostgreSQL, Kafka и все сервисы приложения.

После запуска frontend доступен на порту `80`.

Остановить приложение:

```bash
docker compose -f docker-compose.prod.yml down
```

## Локальная разработка

Для локальной разработки PostgreSQL и Kafka запускаются через отдельный compose-файл:

```bash
docker compose -f docker-compose.dev.yml up -d
```

После этого сервисы проекта запускаются локально через IDE (без участия фронтенда):

- `task-tracker-backend`
- `task-tracker-scheduler`
- `task-tracker-email-sender`
- `task-tracker-summarization`

***

Спасибо за внимание к проекту