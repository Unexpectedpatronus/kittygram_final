# Kittygram

### Как развернуть проект локально в контейнерах:

Создать директорию Kittygram со следующими файлами:
- docker-compose.production.yml
- .env (по образцу .env.example)

#### Выполнить команды в терминале из директории Kittygram:

Запуск сборки контейнеров:
```
docker compose -f docker-compose.production.yml up -d 
```
Выполнение миграций:
```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
Сбор статики проекта и копирование в связанную с контейнерами директорию:
```
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic 
```
```
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```
Создание суперпользователя:
```
docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser 
```

#### Если не хватает места на диске:
Команда для очистки кеша npm:
```
npm cache clean
```
Команда для очистки кеша APT: 
```
sudo apt-get clean
```
Также:
```
sudo docker system prune -a
```
```
sudo journalctl --vacuum-size=100M
```
```
sudo journalctl --vacuum-time=1d
```
```
sudo journalctl --vacuum-files=10
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