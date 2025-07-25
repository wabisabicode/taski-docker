# taski-docker

A simple task tracker used to demonstrate deployment in production environment.

You can check the functionality on https://polarstern13.de/

Github Actions is setup for automatic deployment on the server. It also sends a message with the result of the deployment to the Telegram-bot, specified in GitHub Secrets.

## Technology stack
[![Django](https://img.shields.io/badge/-Django-092E20?style=flat&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/)
[![Docker Compose](https://img.shields.io/badge/-Docker--compose-2496ED?style=flat&logo=docker&logoColor=white)](https://docs.docker.com/compose/)
[![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)](https://github.com/features/actions)

## Local machine deployment
You can run the tracker on your local machine:
```
cd infra/
docker compose -f docker-compose.production.yml up -d
```

For successful deployment, you have to create an `.env` file in the project's root and set the values of its variables. For local deployment, please, comment out the variable `ALLOWED_HOSTS_BACKEND`

### Example of .env file:
```
# Database setup
POSTGRES_USER=
POSTGRES_PASSWORD=
POSTGRES_DB=
# For django:
DB_HOST=
DB_PORT=5432
DJANGO_SECRET_KEY='some_secret_key'
# Production host:
ALLOWED_HOSTS_BACKEND="XXX.XXX.XXX.XXX, example-domain.com"
DEBUG_MODE=True
```                                  

The frontend of the project was prepared by Yandex-Practicum. 

