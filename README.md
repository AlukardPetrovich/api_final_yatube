# api_final
### Для чего этот проект:
Проект предназначен для предоставления доступа через API к социальной сети Yatube.
Предоставляется возможность создания и получения сообщений(posts) и комментариев к ним(comments), публикация сообщений с учетом группы(group), а также создание подписок авторов и получение списка подписок. Полный функционал описан в документации в формате Redoc.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:AlukardPetrovich/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 yatube_api/manage.py runserver
```

### Примеры:

#### запрос:
'get' http://127.0.0.1:8000/api/v1/posts/
#### ответ:
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```

#### запрос:
'post' http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/
```
{
"text": "string"
}
```
#### ответ:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
#### запрос:
'post' http://127.0.0.1:8000/api/v1/jwt/create/
```
{
  "username": "string",
  "password": "string"
}
```
#### ответ:
```
{
  "refresh": "string",
  "access": "string"
}
```
