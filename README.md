# Django Quickstart

Simple Django template for Heroku

## Usage

Create project:

```
django-admin startproject --template https://github.com/henriquebastos/django-quickstart/archive/master.zip --name=Procfile,.env myproject
```

Setup:

```
cd myproject
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Deploy:

```
PRJ=myapp && \
git init && \
git add . && \
git commit -m 'Initial import' && \
heroku create $PRJ && \
heroku config:set DEBUG=True SECRET_KEY=`cat .env | grep SECRET_KEY | cut -d = -f 2` && \
git push heroku master
```
