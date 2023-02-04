FROM python:3.8.3-slim-buster

WORKDIR /app

COPY ./mysite/requirements.txt .

RUN pip install --upgrade pip

RUN pip install -r requirements.txt

COPY . .

RUN cp ./mysite/.env.example ./mysite/.env

RUN python ./mysite/manage.py makemigrations

RUN python ./mysite/manage.py migrate

EXPOSE 8000

CMD ["python", "./mysite/manage.py", "runserver", "0.0.0.0:8000"]
