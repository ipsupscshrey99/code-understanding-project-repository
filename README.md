# Sample Python Repository

A sample Python project demonstrating clean architecture principles using simple, beginner-friendly Python code.

## Directory Structure

```text
sample-python-repository/
├── src/
│   ├── __init__.py
│   ├── main.py
│   ├── calculator.py
│   ├── utils.py
│   ├── models/
│   │   ├── __init__.py
│   │   └── user.py
│   ├── repositories/
│   │   ├── __init__.py
│   │   └── user_repository.py
│   └── services/
│       ├── __init__.py
│       └── user_service.py
├── tests/
│   └── test_calculator.py
├── README.md
├── requirements.txt
└── .graphifyignore
```

## Architecture & Dependency Flow

This project illustrates layered architecture and component interaction:

- **`main.py`**: Entry point executing sample workflows.
  - Depends on `Calculator` for arithmetic operations.
  - Depends on `UserService` to manage user entities.
  - Uses helper utility functions from `utils.py`.
- **Service Layer (`UserService`)**: Contains business logic for creating users and depositing funds.
  - Depends on `UserRepository` for data persistence.
  - Interacts directly with `User` models.
- **Repository Layer (`UserRepository`)**: In-memory data store for saving, reading, and managing `User` entities.
- **Model Layer (`User`)**: Represents the `User` domain model.
- **Utilities (`utils.py`)**: General helper functions like currency formatting and email validation.
- **Calculator (`calculator.py`)**: Simple calculator class demonstrating unit testing and basic class methods.

### Dependency Hierarchy

```text
main.py
  ├── Calculator
  └── UserService
       ├── UserRepository
       │    └── User
       └── User
```

## Running the Application

To run the main demonstration script:

```bash
python src/main.py
```

## Running Tests

You can run tests using Python's built-in `unittest` module:

```bash
python -m unittest discover -s tests
```

Or using `pytest` if installed:

```bash
pytest
```
