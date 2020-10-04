# Django Quickstart

Simple Django template for Heroku

## Usage

Create project:

```
django-admin startproject --template https://github.com/henriquebastos/django-quickstart/archive/master.zip --name=Procfile,.env myproject
```

Deploy:

```
git init
git add .
git commit -m 'Import'

heroku create:app myapp
heroku config:set SECRET_KEY=`cat .env | grep SECRET_KEY | cut -d = -f 2`

git push heroku master
```
