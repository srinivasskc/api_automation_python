# People API

A REST API application for managing people records, built with Flask and Connexion.

## 📖 Overview

This project provides a RESTful API for managing a simple people record database. It includes features for CRUD operations, Swagger documentation, and a web interface.

## 🛠️ Tech Stack

- **Framework**: Flask + Connexion
- **Database**: SQLAlchemy (ORM)
- **API Documentation**: Swagger/OpenAPI
- **Testing**: pytest with mock server support

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- pipenv (recommended) or pip

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd people-api
   ```

2. Install dependencies using pipenv (recommended):
   ```bash
   pipenv shell
   pipenv install
   ```

   Or using pip:
   ```bash
   pip install -r Pipfile
   ```

3. Start the server:
   ```bash
   python server.py
   ```

4. Access the API documentation:
   - Swagger UI: `http://127.0.0.1:5000/api/ui/`
   - Web Interface: `http://127.0.0.1:5000/`

> **Note**: On Windows, use `127.0.0.1` instead of `0.0.0.0` for better compatibility.

## 📁 Project Structure

```
people-api/
├── server.py              # Main application entry point
├── people.py              # People API CRUD operations
├── models.py               # SQLAlchemy database models
├── build_database.py      # Database initialization script
├── config.py              # Configuration settings
├── swagger.yml             # OpenAPI/Swagger specification
├── README.md              # This file
├── LICENSE                # License file
│
├── users/                 # User-related modules
│   ├── __init__.py
│   ├── constants.py       # User constants
│   ├── mocks.py           # Mock data for testing
│   └── services.py        # User service logic
│
├── covid_tracker/         # COVID-19 tracking module
│   ├── covid_tracker.py  # COVID tracker implementation
│   └── cases_summary.xml  # COVID cases data
│
├── static/                # Static assets
│   ├── css/
│   │   └── home.css
│   └── js/
│       └── home.js
│
├── templates/              # HTML templates
│   ├── __init__.py
│   └── home.html
│
├── tests/                 # Test suite
│   ├── __init__.py
│   └── test_mock_server.py
│
└── postman/               # Postman collections
    ├── People.postman_collection.json
    ├── people.postman_environment.json
    ├── covid.postman_collection.json
    └── covid.postman_environment.json
```

## 🔌 API Endpoints

### People API

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/people` | Get all people |
| GET | `/api/people/{id}` | Get person by ID |
| POST | `/api/people` | Create new person |
| PUT | `/api/people/{id}` | Update person |
| DELETE | `/api/people/{id}` | Delete person |

### COVID Tracker API

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/covid` | Get COVID-19 data |

## 🧪 Testing

Run tests using pytest:
```bash
pytest tests/
```

## 📦 Postman Collection

Import the Postman collections from the `postman/` folder to test the API:
- `People.postman_collection.json` - People API tests
- `covid.postman_collection.json` - COVID tracker tests

## 🔧 Common Issues & Solutions

### Swagger UI Installation
To install Swagger-UI, run:
```bash
pipenv install "connexion[swagger-ui]"
```
> **Note**: On Windows with zsh, the URL must be quoted.

### Windows-Specific Notes
- Use `127.0.0.1` as the host instead of `0.0.0.0`
- When using curl, enclose URLs in double quotes instead of single quotes

## 📚 References

This project follows the Real Python tutorial series by [Doug Farrell](https://realpython.com/team/dfarrell/):

- [Part 1: Building API and simple app with connexion, flask](https://realpython.com/flask-connexion-rest-api/#what-rest-is)
- [Part 2: Adding database and ORM (SQL Alchemy)](https://realpython.com/flask-connexion-rest-api-part-2/#author)

## 📄 License

See the [LICENSE](LICENSE) file for details.