#базовый слой
FROM python:3.10 

#в образе переходим в директорию /app (если ее нет - будет создана)
WORKDIR /app

RUN pip install gunicorn==20.1.0
#копируем зависимости
COPY requirements.txt .

#выполняем команду в терминале. скачиваем зависимости
RUN pip install -r requirements.txt --no-cache-dir

#копируем все из текущей директории в /app
COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
