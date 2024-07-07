    FROM python:3.10-slim
    
    # Set environment variables
    ENV PYTHONDONTWRITEBYTECODE 1
    ENV PYTHONUNBUFFERED 1
    
    # Set the working directory in the container
    WORKDIR /app
    
    # Install Poetry
    RUN pip install poetry
    
    # Copy only the dependency files to optimize caching
    COPY poetry.lock pyproject.toml /app/
    
    # Install dependencies
    RUN poetry config virtualenvs.create false \
        && poetry install --no-dev --no-interaction --no-ansi
    
    # Copy the application code into the container
    COPY . /app/
    
    # Expose the port where FastAPI runs (adjust if necessary)
    EXPOSE 8000
    
    # Set environment variables
    ENV DOMAIN=13.49.177.138
    ENV ENVIRONMENT=local
    ENV PROJECT_NAME="Full Stack FastAPI Project"
    ENV STACK_NAME=full-stack-fastapi-project
    ENV BACKEND_CORS_ORIGINS="http://localhost,http://localhost:5173,https://localhost,https://localhost:5173,http://13.60.64.4,http://alexinhngdevops.mooo.com,https://alexinhngdevops.mooo.com,http://alexin_hng.mooo.com,https://13.60.64.4,https://alexin_hng.mooo.com"
    ENV SECRET_KEY=nowahala
    ENV FIRST_SUPERUSER=devops@hng.tech
    ENV FIRST_SUPERUSER_PASSWORD=devops#HNG11
    ENV USERS_OPEN_REGISTRATION=True
    ENV SMTP_HOST=
    ENV SMTP_USER=
    ENV SMTP_PASSWORD=
    ENV EMAILS_FROM_EMAIL=info@example.com
    ENV PYTHONPATH=/app
    ENV SMTP_TLS=True
    ENV SMTP_SSL=False
    ENV SMTP_PORT=587
    ENV POSTGRES_SERVER=db
    ENV POSTGRES_DB=hng11devops2
    ENV POSTGRES_USER=alexin
    ENV POSTGRES_PASSWORD=freakingtired

    CMD poetry run bash ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000