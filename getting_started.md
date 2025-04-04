### Installing django

- Install django: `python3 -m pip install django`
- Install virtual env: `python3 -m venv venv`
- Activate the virtual environment: `source venv/bin/activate`
- Install django: `pip install django`

### Create a project
- List all django-admin commands: `django-admin help`
- Create your project: `django-admin startproject [project name]`
- Create your app: `django-admin startapp [app name]`

### Register the app
- In settings.py file in the project directory, add your app name to INSTALLED APPS:
    ```
    INSTALLED_APPS = [
    '[app name]',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    ]
    ```