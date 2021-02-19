# Test_Django

## Create a project

```shell
django-admin startproject polls
```

## running project

```shell
python3 manage.py runserver 8080
```

## Creating the Polls app

```shell
python3 manage.py startapp polls
```

## db migration

```shell
python3 manage.py migrate # 현재 있는 entity를 db에 migrate
python3 manage.py makemigrations polls #  setting.py > INSTALLED_APPS: polls label을 migration하기 위한 entity file 생성
python3 manage.py sqlmigrate polls 0001 # 만들어진 entity file를 이용, 연결된 SQL에 맞는 query를 생성
```

## invoke Python shell

```shell
python3 manage.py shell # for manual
```

## Create an admin User

```shell
python3 manage.py createsuperuser
```

## Testing in Django

```shell
python3 manage.py test polls
```

## Packaging app

- ref <https://docs.djangoproject.com/en/3.1/intro/reusable-apps/>

```shell
python3 setup.py sdist
python3 -m pip install --user django-polls/dist/django-polls-0.1.tar.gz
python3 -m pip uninstall django-polls
```

### result

```shell
[13:56][NamgiuicBookPro ~/Desktop/GitHub/django-polls]
# python3 -m pip install --user dist/django-polls-0.1.tar.gz
Processing ./dist/django-polls-0.1.tar.gz
Using legacy 'setup.py install' for django-polls, since package 'wheel' is not installed.
Installing collected packages: django-polls
    Running setup.py install for django-polls ... done
Successfully installed django-polls-0.1
[13:57][NamgiuicBookPro ~/Desktop/GitHub/django-polls]
# python3 -m pip uninstall django-polls
Found existing installation: django-polls 0.1
Uninstalling django-polls-0.1:
  Would remove:
    /Users/lonie/Library/Python/3.9/lib/python/site-packages/django_polls-0.1-py3.9.egg-info
    /Users/lonie/Library/Python/3.9/lib/python/site-packages/polls/*
Proceed (y/n)? y
  Successfully uninstalled django-polls-0.1
```

## Deploy app into pythonanywhere

1. Upload Code from Github

```shell
git clone <github_url>
```

1. Create a virtualenv and install Django and any other requirements

```shell
mkvirtualenv --python=/usr/bin/python3.8 polls-virtualenv
(polls-virtualenv)$ pip install django
# or, if you have a requirements.txt:
(polls-virtualenv)$ pip install -r requirements.txt
```

1. Setting up your Web app and WSGI file

- The path to your Django project's top folder -- the folder that contains "manage.py", eg /home/Ronnie89/polls
- The name of your project (that's the name of the folder that contains your settings.py), eg polls
- The name of your virtualenv, eg polls-virtualenv

> case sensitive: path를 잘 봐야한다.

1. Using MySQL

```shell
mysql -u USERNAME -h HOSTNAME -p 'USERNAME$DATABASENAME'

# Django 사용시 > project.setting.py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': '<your_username>$<your_database_name>',
        'USER': '<your_username>',
        'PASSWORD': '<your_mysql_password>',
        'HOST': '<your_mysql_hostname>',
    }
}
```

1. Deployment Static Files

```shell
STATIC_URL = '/static/'
STATIC_ROOT = "/var/www/ronnie89.pythonanywhere.com/static/"
python3 manage.py collectstatic
```
