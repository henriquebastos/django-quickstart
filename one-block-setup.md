# This is a one block installation of Django Quickstart Template

### IMPORTANT: Don't forget to specify the names placeholder, not doing so may cause errors.

```
DJANGO_PROJECT_NAME=my_django_project   && \
HEROKU_APP_NAME=my-heroku-project       && \
python -m venv .venv                    && \
source .venv/bin/activate               && \
pip install django                      && \
django-admin startproject --template https://github.com/henriquebastos/django-quickstart/archive/master.zip --name=Procfile,.env $DJANGO_PROJECT_NAME . && \
pip install -r requirements.txt         && \
git init                                && \
git add .                               && \
git commit -m 'Initial import'          && \
heroku create $HEROKU_APP_NAME          && \
heroku config:set DEBUG=True SECRET_KEY=`cat .env | grep SECRET_KEY | cut -d = -f 2` ALLOWED_HOSTS="*" && \
git push heroku master
```
