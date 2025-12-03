# Django WSGI PostgreSQL Tailwind CSS Template

A robust and production-ready template to start Django projects with modern development best practices.

## 📋 About the Template

The **django-wsgi-psql-tailwindcss-template** is a complete starter template (boilerplate) for Django applications, integrating modern technologies and professional development tools:

- **Django**: Powerful and versatile Python web framework
- **WSGI**: Web Server Gateway Interface for production with Gunicorn
- **PostgreSQL**: Robust and scalable database
- **Tailwind CSS**: Utility-first CSS framework for responsive design
- **Docker & Docker Compose**: Containerization for development and production
- **uv**: Fast Python package manager
- **Ruff**: High-performance Python linter/formatter

## How to run the project (development mode)

1. Clone the repository:
    ```bash
    $ git clone https://github.com/nando2003/django-wsgi-psql-tailwindcss-template.git
    ```

2. Install the dependencies:
    ```bash
    $ uv sync
    $ npm install
    ```

3. Set up the environment variables:
    ```bash
    $ cp .env.example .env
    # Edit the .env file to set your environment variables
    ```

4. Generate a Django secret key and set it in the `.env` file:
   ```bash
   $ uv run python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
   ```

5. Run the development container:
    ```bash
    $ docker compose up --build
    ```

6. Apply database migrations:
    ```bash
    $ docker compose exec app uv run --no-sync manage.py migrate
    ```

7. Run the tailwind watch:
   ```bash
    $ npm run watch
    ```

## How to run the project (production mode)

1. Change DJANGO_ENV to production in the .env file.

2. Build and run the production container:
    ```bash
    $ docker compose -f docker-compose.prod.yml up --build -d
    ```
