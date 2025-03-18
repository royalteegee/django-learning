# django-learning
This is a repository that has documentation on my django learnings 

### Django Folder structure

```python
myproject/                # Root folder of the project
│── manage.py             # Django command-line utility
│── db.sqlite3            # SQLite database (if used)
│── requirements.txt      # Dependencies (if using virtualenv)
│── .env                  # Environment variables (if used)
│── myproject/            # Project package (contains settings)
│   │── __init__.py       # Marks this directory as a Python package
│   │── asgi.py           # ASGI entry point (used for async servers)
│   │── settings.py       # Project settings
│   │── urls.py           # URL routing for the project
│   │── wsgi.py           # WSGI entry point (used for deployment)
│
│── apps/                 # (Optional) Store all Django apps here
│   │── myapp/            # A Django app
│   │   │── __init__.py   # Marks this as a Python package
│   │   │── admin.py      # Django admin configurations
│   │   │── apps.py       # App configuration
│   │   │── models.py     # Database models
│   │   │── views.py      # Views (controllers)
│   │   │── forms.py      # Django forms (optional)
│   │   │── urls.py       # App-specific URLs
│   │   │── tests.py      # Unit tests
│   │   │── serializers.py # (For DRF, if using Django REST Framework)
│   │   │── migrations/   # Database migrations
│   │   │   │── __init__.py
│   │   │   │── 0001_initial.py
│
│── static/               # Static files (CSS, JS, Images)
│── media/                # Uploaded media files (user uploads)
│── templates/            # Global HTML templates
│── logs/                 # (Optional) Store log files here
│── docker/               # (Optional) Docker-related configs
│── scripts/              # (Optional) Custom scripts for automation
│── docs/                 # (Optional) Documentation files
```