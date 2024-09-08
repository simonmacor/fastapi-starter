[![CI](https://github.com/simonmacor/fastapi-starter/actions/workflows/ci.yml/badge.svg)](https://github.com/simonmacor/fastapi-starter/actions/workflows/ci.yml)

# FastAPI Starter Kit

**FastAPI Starter Kit** – a base project designed to help you develop web applications using Python and the **FastAPI** framework. This starter kit is built to simplify backend development with a pre-configured architecture for testing, database management, and mocking third-party services.

## Features

- **FastAPI Framework**: A modern and fast framework for building web APIs with Python.
- **BDD Testing with Behave**: Use behavior-driven development (BDD) for scenario-based testing.
- **Unit Testing with Pytest**: Pre-configured for unit and functional tests.
- **SQLAlchemy**: ORM (Object-Relational Mapper) for database interaction.
- **Alembic**: A database schema migration tool for managing schema changes.
- **Mountebank**: Mock third-party services with imposters for integration testing.
- **PostgreSQL**: Latest version of PostgreSQL as the default database.
- **Adminer**: A web-based tool to easily manage the PostgreSQL database.

## Prerequisites

- **Docker** and **Docker Compose** must be installed on your machine.

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/your-project/fastapi-web-starter-kit.git
   cd fastapi-web-starter-kit
   ```

2. Install Python dependencies (if working locally without Docker):

   ```bash
   python3 -m venv env
   source env/bin/activate
   pip install -r requirements.txt
   ```

3. Start the application using Docker Compose:

   ```bash
   docker-compose up --build
   ```

4. Access the FastAPI application at [http://localhost:8000](http://localhost:8000).
5. Access **Adminer** to manage the database at [http://localhost:8080](http://localhost:8080).

## Important Files

- **`requirements.txt`**: Contains the necessary Python libraries.
  - [FastAPI Documentation](https://fastapi.tiangolo.com/)
  - [Behave Documentation](https://behave.readthedocs.io/en/latest/)
  - [Pytest Documentation](https://docs.pytest.org/en/6.2.x/)
  - [SQLAlchemy Documentation](https://docs.sqlalchemy.org/en/14/)
  - [Alembic Documentation](https://alembic.sqlalchemy.org/en/latest/)
  
- **`docker-compose.yml`**: Docker configuration for the application, including PostgreSQL, Adminer, and Mountebank.

- **`alembic/`**: Directory for database migrations using Alembic.

- **`tests/`**: Directory for unit, functional, and BDD tests.

- **`imposters.ejs`**: Configuration file for Mountebank, allowing you to mock third-party services.

## Included Services

### FastAPI

FastAPI is used to create fast and performant RESTful APIs. The application is available at [http://localhost:8000](http://localhost:8000).

- [FastAPI Documentation](https://fastapi.tiangolo.com/)

### PostgreSQL and Adminer

PostgreSQL is the database configured with the latest version, and you can manage it via **Adminer** at [http://localhost:8080](http://localhost:8080).

- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Adminer Documentation](https://www.adminer.org/)

### Mountebank

Mountebank is configured to simulate third-party services and test API integrations. Imposter configuration is stored in the `imposters.ejs` file.

- [Mountebank Documentation](http://www.mbtest.org/docs/gettingStarted)

### Testing

- **BDD with Behave**: BDD scenarios are defined in the `features/` directory.
  - [Behave Documentation](https://behave.readthedocs.io/en/latest/)

- **Unit and Functional Testing with Pytest**: Traditional tests are located in the `tests/` directory.
  - [Pytest Documentation](https://docs.pytest.org/en/6.2.x/)

### Database Migrations

Database schema migrations are managed via Alembic. Use the following commands to create and apply migrations:

```bash
# Create a new migration
alembic revision --autogenerate -m "Migration name"

# Apply migrations
alembic upgrade head
```

- [Alembic Documentation](https://alembic.sqlalchemy.org/en/latest/)

## Useful Commands

- **Start the application:**

  ```bash
  docker-compose up --build
  ```

- **Apply database migrations:**

  ```bash
  docker-compose exec app alembic upgrade head
  ```

- **Run unit and functional tests:**

  ```bash
  docker-compose exec app pytest
  ```

- **Run BDD tests:**

  ```bash
  docker-compose exec app behave
  ```
