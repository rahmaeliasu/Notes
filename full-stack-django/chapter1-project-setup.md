# Django Project Configuration Using pyenv & poetry

Last Edited: November 2, 2025 7:57 AM

- Install pyenv on windows: [https://github.com/pyenv-win/pyenv-win](https://github.com/pyenv-win/pyenv-win) (follow the “Quick Start”)

## Install poetry using pipx

- Install pipx

```bash
pyenv exec pip intsall --user pipx
```

- To ensure pipx runs correctly, run:

```bash
pyenv exec pipx ensurepath

#In case it doesn't work, do:
pyenv exec pipx ensurepath --force
```

- Restart your PowerShell - type `pipx`, and you shouldn’t get errors

> Now installing Poetry - Poetry is a dependency manager and packager for Python.
>

```bash
pipx install poetry # run to install poetry
```

**Stating a new poetry project:**

- Navigate to using the PowerShell to where you want your project to be created

```bash
# run
poetry new <projectname>

cd djangocourse
ls # to check files in that directory
```

## Setup virtual environment & install dependencies

```bash
poetry shell # to enter a Python shell using the poetry project

# to use the virtual environment:
- launch the VSCode command pallete with ctrl + shift + p
- go to Python: Select Interpreter
- find the virtual environment Poetry created for you
```

- Installing dependencies

```bash
poetry install # to install dependencies listed in the pyproject.toml

poetry add django@^5.0.1 # speacify the version
# or just
poetry add django # without specifying the version

poetry run django-admin --version # outputs the version of Django you're using
```

> Notes:
>
>
> `poetry.lock` file defines exactly what was installed - this is useful so that other developers can install the exact same versions of the dependencies.
>

## Starting a django project

```bash
# delete the src folder & run
poetry run django-admin startproject djangocourse . # djangocourse = projectname
```

```bash
# To start the application, run:
poetry run python manage.py runserver
```

## Run migrations, create a superuser and access the admin panel

```bash
# run migrations
poetry run python manage.py migrate

# create a superuser ( a user that can accces the admin panel)
poetry run python manage.py createsuperuser

# finally, run
poetry run python manage.py runserver

# in your browser navigate to the admin panel - "http://127.0.0.1:8000/admin/"
```

## Create a Django app

A Django app is a package that provides a set of features to your Django project.

```bash
poetry run python manage.py startapp <appname>
```
