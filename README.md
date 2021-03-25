# Python: Getting Started

A barebones Django app, which can easily be deployed to Heroku.

This application supports the [Getting Started with Python on Heroku](https://devcenter.heroku.com/articles/getting-started-with-python) article - check it out.

## Running Locally

Make sure you have Python 3.9 [installed locally](https://docs.python-guide.org/starting/installation/). To push to Heroku, you'll need to install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli), as well as [Postgres](https://devcenter.heroku.com/articles/heroku-postgresql#local-setup).

```sh
$ git clone https://github.com/heroku/python-getting-started.git
$ cd python-getting-started

$ Anaconda prompt:
$ python -m venv getting-started
$ pip install -r requirements.txt

$ createdb python_getting_started or createdb -U postgres python_getting_started

$ python manage.py migrate
$ python manage.py collectstatic

$ heroku local (doesn't work on WIN10 - No module named 'fcntl'')
  call this: heroku local web -f Procfile.windows
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

```sh
$ heroku create
$ check: git remote -v
$ heroku git:remote -a ancient-ridge-13440
$ set git remote heroku to https://git.heroku.com/ancient-ridge-13440.git
$ git push heroku main
  It will install:
  - python-3.9.2
  - pip 20.1.1, setuptools 47.1.1 and wheel 0.34.2
  - SQLite3
  - requirements with pip
  
  -r push from a branch: git push heroku BRANCH_NAME:master


$ heroku run python manage.py migrate
$ heroku open
  It will open: https://ancient-ridge-13440.herokuapp.com/
  You can open also: http://localhost:5000/
```
or

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## Documentation

For more information about using Python on Heroku, see these Dev Center articles:

- [Python on Heroku](https://devcenter.heroku.com/categories/python)
