# Kittygram

### Как развернуть проект локально в контейнерах:

Создать директорию Kittygram со следующими файлами:
- docker-compose.production.yml
- .env (по образцу .env.example)

#### Выполнить команды в терминале из директории Kittygram:

Запуск сборки контейнеров:
```
 sudo docker compose -f docker-compose.production.yml up -d 
```
Выполнение миграций:
```
 sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
Сбор статики проекта и копирование в связанную с контейнерами директорию:
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic 
```
```
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```
Создание суперпользователя:
```
 sudo docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser 
```

### Стэк технологий:

При создании проекта использовались следующие технологии:
- Python
- Django framework
- Django-rest-framework
- Node.js
- Docker

### Об авторе:

Автор проекта: Одинцов Е.В.

ссылка на GitHub: [Unexpectedpatronus](https://github.com/Unexpectedpatronus)