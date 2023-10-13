# О проекте

Проект по получению вопросов для викторины с публичного API.

Функционал:
* получение от публичного API определенного количества вопросов. 
* получить все записанные вопросы из базы данных.


# Оглавление

[Requirements](#Requirements) <br>
[Запуск проекта](#Запуск-проекта) <br>
[Создание среды разработки](#Создание-сред-разработки) <br>
[Используемые технологии](#Используемые-технологии) <br>

# Requirements

* Python 3.10
* Docker 20.10+ [(инструкция по установке)](https://docs.docker.com/get-docker/).

# Клонирование репозитория
Склонируйте репозиторий git clone git@github.com:SergoSolo/quiz_questions.git

# Запуск проекта

Все команды выполняются из корневой директории проекта.

<details>
<summary>Проверка docker</summary>
<br>
По умолчанию проект запускается в докере. Для начала нужно убедиться, что докер
установлен. Открой любой терминал и выполни следующую команду:

```shell
docker --version
```
Должна быть выведена версия докера, это выглядит примерно так:
```
Docker version 20.10.21, build baeda1f
```
Если докер не установлен, то установите его, следуя [инструкции](https://docs.docker.com/get-docker/).
</details>

<details>
<summary>Настройка переменных окружения</summary>
<br>

Переменные окружения проекта хранятся в файле `.env` , для которого есть шаблон `.env.template`.
Создай в корне проекта файл `.env` простым копированием файла `.env.template`.

</details>

<details>
<summary>Запуск сервисов</summary>
<br>
<hr>

Для запуска проекта выполни следующую команду:
```
docker-compose up --build -d
```

Убедимся, что все контейнеры запущены:
```
docker-compose ps
```

Результат должен быть примерно такой (список сервисов может отличаться, но статус всех сервисов
должен быть `running`):
```
NAME                COMMAND                  SERVICE             STATUS              PORTS
quiz_api            "sh -c 'alembic upgr…"   api                 running             0.0.0.0:8000->8000/tcp
quiz_db             "docker-entrypoint.s…"   db                  running             0.0.0.0:5432->5432/tcp
```

Каждый ресурс описан в документации: точки доступа (адрес для выполнения запроса), типы запросов, вспомогательные параметры.
Проект с полным описанием доступен по ссылке http://localhost:8000/docs или http://localhost:8000/redoc.

Остановить и удалить запущенные контейнеры:
```
docker-compose down
```
</details>

##  Используемые технологии:
- Python version 3.10
- FastAPI
- Alembic
- SQLAlchemy
- Pydantic
- Aiohttp


## Автор:
> [Sergey](https://github.com/SergoSolo)