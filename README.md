# API для YaTube

### Описание:
API для проекта YaTube позволяет пользователям соверашть разные действия на сайте, при этом не посещая его.

### С помощью API можно:
 - Смотреть, писать, редактировать и удалять посты.
 - Комментировать посты, а так-же читать, редактировать и удалять комментарии.
 - Создавать сообщества и просматривать информацию о них.
 - Подписываться на авторов.

### Примеры запросов к API:
##### Получение публикации:
- Request: GET http://127.0.0.1:8000/api/v1/posts/3/
- Response samples:
    ```
    {
        "id": 3,
        "author": "Shoyo",
        "text": "Third post",
        "pub_date": "05.08.2022 10:35:53",
        "image": null,
        "group": null
    }
    ```
##### Список сообществ:
- Request: GET http://127.0.0.1:8000/api/v1/groups/
- Response samples:
    ```
    [
        {
            "id": 1,
            "title": "Learning",
            "slug": "learning",
            "description": "A group where you can ask questions about learning"
        }
    ]
    ```
##### Добавление комментария:
- Request: POST http://127.0.0.1:8000/api/v1/posts/3/comments/
- Request samples:
     ```
    {
        "text": "Adding a comment via the API"
    }
     ```
- Response samples:
    ```
    {
        "id": 1,
        "author": "Shoyo",
        "text": "Adding a comment via the API",
        "created": "05.08.2022 10:36:31",
        "post": 3
    }
    ```
##### Подписаться на пользователя:
- Request: POST http://127.0.0.1:8000/api/v1/follow/
- Request samples:
    ```
    {
        "following": "Tobio"
    }
    ```
- Response samples:
    ```
    {
        "user": "Shoyo",
        "following": "Tobio"
    }
    ```
##### Получение JWT-токена:
- Request: POST http://127.0.0.1:8000/api/v1/jwt/create/
- Request samples:
    ```
    {
        "username": "Shoyo",
        "password": "string"
    }
    ```
- Response samples:
    ```
    {
        "refresh": "Data to refresh the token",
        "access": "Token"
    }
    ```

### Как запустить проект:

Клонировать репозиторий и перейти в него.

-
    ```
    git clone git@github.com:clownvkkaschenko/api_final_yatube.git
    ```
-
    ```
    cd api_final_yatube
    ```

Cоздать и активировать виртуальное окружение:

-
    ```
    python -m venv venv
    ```
-
    ```
    source venv/Scripts/activate
    ```
Установить зависимости из файла requirements.txt:

-
    ```
    python -m pip install --upgrade pip
    ```
-  
    ```
    pip install -r requirements.txt
    ```

Выполнить миграции:

-
    ```
    python manage.py migrate
    ```

Запустить проект:

-
    ```
    python manage.py runserver
    ```

### Используемые технологии:
- [Python 3.7.9](https://www.python.org/)
- [Django 2.2.16](https://www.djangoproject.com/)
- [Django Rest Framework 3.12.4](https://www.django-rest-framework.org/)
- [djoser 2.1.0](https://djoser.readthedocs.io/en/latest/getting_started.html)
- [Simple JWT 4.7.2](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/)

### Документация к API:
- http://127.0.0.1:8000/redoc/

### Автор:
Иван Конышкин