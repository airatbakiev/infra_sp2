FROM python:3.7-slim

# Cоздать директорию приложения.
RUN mkdir /app

# Скопировать содержимое директории /api_yamdb c локального компьютера
# в директорию /app.
COPY ./ /app

# Скопировать с локального компьютера файл зависимостей
# в директорию /app/yamdb.
#COPY ../api_yamdb/requirements.txt /app/api_yamdb

#WORKDIR /app/api_yamdb

# Выполнить установку зависимостей внутри контейнера.
RUN pip3 install -r /app/requirements.txt --no-cache-dir

# Сделать директорию /api_yamdb рабочей директорией. 
WORKDIR /app

# Выполнить запуск сервера разработки при старте контейнера.
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000"]