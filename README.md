# Django CRUD User Management

A simple Django application for managing user records with full CRUD operations and profile image uploads.

## Features

- List all user records
- Create a new user
- View a user's details
- Edit an existing user
- Delete a user
- Upload and display a profile photo
- Store data in MySQL using Django's ORM
- Use a Django `ModelForm` for validation and form rendering

## CRUD Workflow

The application manages records through the `User` model, which contains:

- Name
- Photo
- Email
- Password
- Mobile number
- Date of birth

The `UserForm` is based on this model and handles form input for creating and editing records. The views use Django's ORM to retrieve, create, update, and delete records.

## Routes

| URL | Operation |
| --- | --- |
| `/` | List users |
| `/Add/` | Create a user |
| `/View/<id>` | View a user |
| `/Edit/<id>` | Edit a user |
| `/Delete/<id>` | Delete a user |
| `/admin/` | Django administration |

Uploaded images are stored in the `media/uploads/` directory and are served during development when `DEBUG = True`.

## Project Structure

```text
project/
├── manage.py
├── project/
│   ├── settings.py
│   └── urls.py
└── myapp/
    ├── models.py
    ├── forms.py
    ├── views.py
    ├── urls.py
    ├── migrations/
    └── templates/
        ├── Add.html
        ├── Delete.html
        ├── Edit.html
        ├── Listingpage.html
        └── View.html
```

## Requirements

- Python 3.14 or a compatible Python version
- Django
- MySQL server
- PyMySQL and Pillow

The project uses PyMySQL as the MySQL driver. The adapter is registered in `project/project/__init__.py` so Django can use it through the MySQL backend.

## Setup

1. Clone the repository and enter the project directory:

   ```bash
   git clone https://github.com/mianohh/django_crud.git
   cd django_crud/project
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

3. Install the dependencies:

   ```bash
   pip install django pymysql pillow
   ```

4. Create the MySQL database configured in `project/settings.py`, then update the database connection values for your local environment.

5. Apply migrations:

   ```bash
   python manage.py migrate
   ```

6. Start the development server:

   ```bash
   python manage.py runserver
   ```

7. Open `http://127.0.0.1:8000/` in your browser.

## Development Notes

- Run management commands from the directory containing `manage.py`.
- The current project serves uploaded media only in development mode.
- Do not commit real database passwords or secret keys. Use environment variables before deploying or publishing sensitive configuration.
- The Django development server is intended for local development, not production use.

## License

This project is available for learning and development purposes.
