# samarafurniture
## Установка необходимых инструментов

1. Установите Python:
``` 
sudo apt-get update
sudo apt-get install python3.8
sudo apt-get install python3-pip
```

2. Установите PostgreSQL:
```
sudo apt-get install postgresql postgresql-contrib
```

3. Установите Git:
```
sudo apt-get install git
```

## Настройка проекта

1. Склонируйте проект с GitHub:
```
git clone https://github.com/your-repo-name/your-project-name.git
```

2. Перейдите в каталог проекта:
```
cd your-project-name
```

3. Создайте и активируйте виртуальное окружение:
```
python3 -m venv env
source env/bin/activate
```

4. Установите зависимости:
```
pip install -r requirements.txt
```

5. Создайте базу данных PostgreSQL для вашего проекта:
```
sudo -u postgres createdb your-db-name
```

6. Отредактируйте файл конфигурации приложения (например, config.py) и введите данные для подключения к базе данных PostgreSQL:
```
SQLALCHEMY_DATABASE_URI = 'postgresql://postgres:password@localhost/your-db-name'
```

## Запуск приложения Flask

1. Примените миграции базы данных:
```
flask db init
flask db migrate -m "initial migration"
flask db upgrade
```

2. Запустите приложение Flask:
```
export FLASK_APP = myapp.py
export FLASK_ENV = development
flask run --port=8080 --host=0.0.0.0
```

3. Откройте браузер и перейдите по URL-адресу http://your-server-ip-address:8080, чтобы просмотреть свой сайт.

## Настройка Nginx

1. Установите Nginx:
```
sudo apt-get install nginx
```

2. Создайте конфигурационный файл в /etc/nginx/sites-available:
```
sudo nano /etc/nginx/sites-available/your-site-name
```

3. Вставьте следующий код в ваш файл конфигурации:
```
server {
    listen 80;
    server_name your-server-name.com www.your-server-name.com;

    location / {
        include proxy_params;
        proxy_pass http://127.0.0.1:8080;
    }
}
```

4. Включите файл конфигурации:
```
sudo ln -s /etc/nginx/sites-available/your-site-name /etc/nginx/sites-enabled/
```

5. Проверьте конфигурационный файл Nginx:
```
sudo nginx -t
```

6. Перезапустите Nginx:
```
sudo systemctl restart nginx
```

7. Посетите свой сайт, перейдя по URL-адресу вашего сервера, чтобы увидеть, как он работает.
