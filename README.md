# API для YaTube

### Описание:
API для проекта YaTube позволяет пользователям соверашть разные действия на сайте, при этом не посещая его

### С помощью API можно:
 - Смотреть, писать, редактировать и удалять посты
 - Комментировать посты, а так-же читать, редактировать и удалять комментарии
 - Создавать сообщества и просматривать информацию о них
 - Подписываться на авторов

### Примеры запросов к API:
- /api/v1/posts/ - Получить список публикаций или создать новую публикацию
- /api/v1/posts/{id}/ - Получить, изменить или удалить пост по его id
- /api/v1/posts/{post_id}/comments/ - Получить все комментарии или написать новый комментарий к определённому посту
- /api/v1/posts/{post_id}/comments/{id}/ - Получить, изменить или удалить определённый комментарий к публикации по id
- /api/v1/follow/ - Возвращает все подписки пользователя, сделавшего запрос
- /api/v1/jwt/create/ - Получение JWT-токена(в теле запроса нужно передать имя и пароль пользователя)

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