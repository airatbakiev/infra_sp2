### Как запустить проект:

Клонировать репозиторий:

```
git clone https://github.com/airatbakiev/infra_sp2.git
```

Перейти в папку infra и запустить docker-compose.yaml
(при установленном и запущенном Docker)
```
cd infra_sp2/infra
docker-compose up
```

Для пересборки контейнеров выполнять команду:
(находясь в папке infra, при запущенном Docker)
```
docker-compose up -d --build
```

В контейнере web выполнить миграции:

```
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:

```
docker-compose exec web python manage.py createsuperuser
```

Собрать статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```

Проверьте работоспособность приложения, для этого перейдите на страницу:

```
 http://localhost/admin/
```

Запросы для работа с API:

```
 http://localhost/redoc/
```

Авторы проекта:

```
Айрат Бакиев, Виталий Яремчук, Максим Никулин
```

### Лицензия
[MIT](./LICENSE)