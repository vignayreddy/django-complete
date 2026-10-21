# Django Basics — Learning Project

A beginner-friendly Django project to learn project setup, virtual environments, database migrations, app creation, and Django admin configuration.

## 1. Create a Virtual Environment

Create a virtual environment to keep project dependencies separate.

```bash
python -m venv django_basics
```

## 2. Activate the Virtual Environment

**Windows PowerShell:**

```powershell
.\django_basics\Scripts\Activate.ps1
```

After activation, your terminal should show `(django_basics)`.

## 3. Install Django

```bash
python -m pip install django
```

## 4. Check Installed Libraries and Frameworks

To list all installed Python packages:

```bash
pip freeze
```

To save the installed packages to a file:

```bash
pip freeze > requirements.txt
```

## 5. Create a Django Project

Create a project named `learning` in the current directory:

```bash
django-admin startproject learning .
```

The `.` tells Django to create the project in the current directory instead of creating another nested folder.

## 6. Run the Development Server

```bash
python manage.py runserver
```

Open the following URL in your browser:

http://127.0.0.1:8000/

## 7. Apply Database Migrations

Run the following command to apply Django's initial database migrations:

```bash
python manage.py migrate
```

This creates the required database tables for built-in Django apps and helps prevent errors related to unapplied migrations.

## 8. Create a Superuser

Create an administrator account to access the Django admin panel:

```bash
python manage.py createsuperuser
```

Enter the requested username, email address (if required), and password when prompted.

**Example credentials for local practice:**

- Username: `Vignay`
- Password: `vinnu123`

*Security note: These are example development credentials. Use a strong, unique password and never use these credentials in production.*

## 9. Create a Django App

Create an app named `students`:

```bash
python manage.py startapp students
```

## 10. Register the App in `settings.py`

Open `learning/settings.py` and add `students` to `INSTALLED_APPS`:

```python
INSTALLED_APPS = [
    # Default Django apps
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # Custom apps
    'students',
]
```

## 11. Create Database Migrations

After creating or modifying models in `students/models.py`, run:

```bash
python manage.py makemigrations
```

This generates migration files inside the app's `migrations/` directory. These files describe changes to your database schema.

## 12. Apply Migrations to the Database

```bash
python manage.py migrate
```

This applies pending migrations and updates the database schema.

**Remember:**
- `makemigrations` creates migration files.
- `migrate` applies those migrations to the database.

## 13. Register a Model in Django Admin

Open `students/admin.py` and register your model.

For example, if you have a model named `Student` in `students/models.py`:

```python
from django.contrib import admin
from .models import Student

admin.site.register(Student)
```

This makes the `Student` model available in the Django admin panel.

## 14. Access the Django Admin Panel

Start the server:

```bash
python manage.py runserver
```

Visit:

http://127.0.0.1:8000/admin/

Log in using your superuser credentials.

## Common Django Commands

| Command | Purpose |
|---|---|
| `python -m venv django_basics` | Create a virtual environment |
| `python -m pip install django` | Install Django |
| `pip freeze` | List installed packages |
| `django-admin startproject learning .` | Create a Django project |
| `python manage.py runserver` | Start the development server |
| `python manage.py createsuperuser` | Create an admin account |
| `python manage.py startapp students` | Create a Django app |
| `python manage.py makemigrations` | Generate migration files |
| `python manage.py migrate` | Apply database migrations |

---
