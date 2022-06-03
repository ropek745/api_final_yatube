# Проект: API для Yatube
Этоn API можно встроить в любой подходящий для этого сервис с целью получения информации о постах, для создания самих постов их изменения и многого другого.

Некоторые возможности будут продемонстрированы ниже в конкретных примерах. 

Для получения полной информации о проекте, разверните его у себя и пройдите по ссылке http://127.0.0.1:8000/redoc/

## Как запустить проект:
1. Клонировать репозиторий и перейти в него в командной строке:

```
git@github.com:ropek745/api_final_yatube.git
cd api_final_yatube
```

2. Cоздать и активировать виртуальное окружение:
```
python3 -m venv env
source env/bin/activate
```

3. Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```

4. Выполнить миграции:
```
python3 manage.py migrate
```

5. Запустить проект:
```
python3 manage.py runserver
```

## Примеры запросов

**1. Получение списка публикаций (GET) - /api/v1/posts/**

Ответ:
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
**2. Получение конкретной публикации (GET) - /api/v1/posts/{id}/**

Ответ:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
**3. Создание публикации (POST) - /api/v1/posts/**

Ответ:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
**4. Получение комментариев (GET) - /api/v1/posts/{post_id}/comments/**

Ответ:
```
[
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "created": "2019-08-24T14:15:22Z",
    "post": 0
  }
]
```
**5. Получение комментария (GET) - /api/v1/posts/{post_id}/comments/{id}/**

Ответ:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
