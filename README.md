#Продуктовый помощник Foodgram

## Описание
«Фудграм» — сайт, на котором пользователи публикуют рецепты, добавляют 
чужие рецепты в избранное и подписываются на публикации других авторов. 
Пользователям сайта также доступен сервис «Список покупок». 
Он позволяет создавать список продуктов, которые нужно купить для приготовления 
выбранных блюд.

## Технологии
- Python
- Docker
- PostgreSQL
- Django REST framework
- Gunicorn
- Nginx
- React

Данные для доступа:
http://84.201.179.25/admin/

login - admin@admin.com
pass - admin

## Необходимо для запуска
[Docker](https://docs.docker.com/engine/install/)

## Запуск проекта локально

Клонировать репозиторий:
```shell
git clone git clone <https or SSH URL>
```

Перейти в каталог проекта:
```shell
cd foodgram-project-react
```

Создать .env:
```shell
touch .env
```

Шаблон содержимого для .env файла:
```shell
# Django settings
DEBUG=False
SECRET_KEY=<django_secret_key>
ALLOWED_HOSTS=127.0.0.1;localhost;<example.com;xxx.xxx.xxx.xxx>

# DB
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB=django
DB_HOST=db
DB_PORT=5432

# Superuser
ADMIN_USERNAME=admin
ADMIN_EMAIL=admin@admin.com
ADMIN_PASSWORD=admin
```

Развернуть приложение:
```shell
docker compose -f docker-compose.dev.yml up -d
```
В процессе развертывания приложения запускается скрипт `backend/up.sh`.
- Собирает статику и копирует в volume.
- Выполняет миграции.
- Создает суперпользователя.
- Создает теги.
- Запускает сервер gunicorn.

Выполнить заполнение базы ингредиентами:
```shell
docker compose exec backend python manage.py load_data_csv
```

После успешного запуска, проект доступен на локальном IP `127.0.0.1:8000`.

# Разработчики
- [Dmitrii-Kuhnin](hhttps://github.com/Dmitrii-Kuhnin) python backend developer
- [Yandex-Prakticum]