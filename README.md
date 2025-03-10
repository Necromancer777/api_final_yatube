# api_final
### Описание проекта:

API для сервиса YATUBE. Позволяет получать список публикаций, комментариев, групп сервиса, создавать публикации и комментарии к постам, подписываться на других пользователей посредством API запросов. Безопасные запросы можно выполнять анонимно, для других запросов нужно получать токен.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Necromancer777/api_final_yatube.git
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

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры использования:

Запрос на получение токена:

```
POST /api/v1/jwt/create/
{
  "username": "string",
  "password": "string"
}
```

Получение публикаций:

```
GET /api/v1/posts/
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

Создание публикации:

```
POST /api/v1/posts/
{
  "text": "string",
  "image": "string",
  "group": 0
}
```

Для просмотра других примеров и более подробного руководство после запуска проекта на локальной машине перейдите:

```
http://127.0.0.1:8000/redoc/
```
