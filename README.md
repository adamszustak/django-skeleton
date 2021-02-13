# Django Skeleton by ImustAdmit

## Main features :skull:

Contains ready-to-go files for working with **poetry, tox, pytest, pre-commit, django-debug-toolbar, pytest-cov**, separated settings (base/local/test/production) with choice about hiding sensitive data and Users app (as recommended by Django).

## How to use it? :skull:

- Starting project (by default it takes the django version from the GLOBAL scope! After installing poetry you can alter django version)

```
$ django-admin startproject --template https://github.com/ImustAdmit/django-skeleton/archive/main.zip \
--name=config.json,pyproject.toml,pytest.ini <your-project-name>
```

- Creating virtual environment using poetry and adding required packages.

```
$ cd <your-project-name>
$ poetry add -D pre-commit, pytest-django, pytest-pythonpath, factory-boy, pytest-cov, tox, django-debug-toolbar
$ poetry add django, psycopg2
```

- Change **authors** line from pyproject.toml (line 41) and rename **gitignore** to **.gitignore**.

```
$ authors = ["John Smith <john@example.com>"]
```

- Go to base settings (project_name/conf/settings/base.py) and choose wheter you want to hide sensitive settings in config.json or in the environment.

Required data: 
> NAME_DB = database name (project name by default)

> USER_DB = username-access to database

> PASS_DB = user password-access to database

Extra data:
> HOST_DB = database host

> PORT_DB = database port


- Prepare project to run.

```
$ cd <your-project-name>
$ poetry run python manage.py makemigrations
$ poetry run python manage.py migrate
$ poetry run python manage.py collectstatic
```

## Additional info :skull:

- Running tests and coverage.

```
$ poetry run pytest
$ poetry run pytest --cov
```

- Installing pre-commit hook.

```
$ git init
$ poetry run pre-commit install
$ poetry run pre-commit run --all-files
```

- Running tests & pre-commit hooks.

```
$ poetry run tox
```
