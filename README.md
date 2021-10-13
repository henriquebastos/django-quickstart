# Django Quickstart

### Deploy a fully configured Django Application the fastest way!

This template includes:
* Easy settings setup with [Decouple](https://github.com/henriquebastos/python-decouple)
* Use of URL's to manage database access
* Static assets serving with dj-static with a WSGI server
* A [one-block setup](https://github.com/henriquebastos/django-quickstart/blob/master/one-block-setup.md) ready to **deploy in seconds** into heroku, 

## Usage

Lets create your project, **you will not clone this repo**, just follow the instructions bellow.

**NOTE**: You may need need to replace _myproject_ placeholder to your project's name, it can break the installation.
```
mkdir myproject
cd myproject
python -m venv .venv
source .venv/bin/activate
pip install django
```

Now we can pull Django Quickstart Structure to Project 

```
django-admin startproject --template https://github.com/henriquebastos/django-quickstart/archive/master.zip --name=Procfile,.env myproject .
```

And then, proceed with the installation of quickstart's requirements. 

```

pip install -r requirements.txt
```

Last but not least, deploy our app in heroku:

**IMPORTANT**: Before doing so, you will need to install and login into [heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)


```
git init
git add .
git commit -m 'Initial import'
heroku create myproject
heroku config:set DEBUG=True SECRET_KEY=`cat .env | grep SECRET_KEY | cut -d = -f 2` ALLOWED_HOSTS="*"
git push heroku master
```
