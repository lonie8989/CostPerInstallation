# Test_Django

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
