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
# people-api

Hello 👋🏻,

This is a REST API with that simulates a simple people record database. Post following the setup
instructions, you may want to play around with the API's in either swagger or with the provided
postman collections in `/postman` folder. Enjoy and happy testing.

## Tech stack

Uses Flask, Connexion, Swagger and SQL Alchemy

## Setup

- Ensure you have pipenv available. Read this
  [blog](https://automationhacks.io/2020/07/12/how-to-manage-your-python-virtualenvs-with-pipenv/)
  to understand all about pipenv
- Ensure you have cloned this repo and are in the project root directory that has the `Pipfile` with
  definitions of all required dependencies.
- Execute `pipenv shell` to activate the virtualenv in your terminal
- Execute `pipenv install` to install all dependencies
- Execute `python server.py`
- To open swagger navigate to `http://0.0.0.0:5000/api/ui/`

> On a windows machine, you may want to replace the host as `127.0.0.1` in above URL

## Project structure

- `server.py` - Entry point to start the Flask app with Connexion
- `config.py` - Flask app configuration and database setup
- `people.py` - CRUD operations for the People API
- `models.py` - SQLAlchemy database models
- `build_database.py` - Script to initialize the database
- `swagger.yml` - Swagger spec defining API routes and documentation
- `users/` - User-related services and constants
- `covid_tracker/` - COVID tracking functionality
- `static/` - CSS and JS files for the web UI
- `templates/` - HTML templates
- `postman/` - Postman collections for API testing
- `tests/` - Unit and integration tests

## Tests

This project includes unit and integration tests.

### Running Tests

```bash
# Run all tests with pytest
pytest

# Run specific test file
pytest tests/test_mock_server.py
```


## Common Gotchas

- To install swagger-ui, please run `pipenv install "connexion[swagger-ui]"`. Read this
  [bug](https://github.com/zalando/connexion/issues/779) to understand about why zsh needs this to
  be quoted.
- If you are on windows platform, 
  - Try using `127.0.0.1` as the host instead of `0.0.0.0`
  - Also enclose the URL in CURL with double quotes instead of single quotes (Reference thread on [stack overflow](https://stackoverflow.com/questions/6884669/curl-1-protocol-https-not-supported-or-disabled-in-libcurl/24232441#24232441)) 

## Reference

This follows the steps from a real python tutorial series written by
[Doug Farrell](https://realpython.com/team/dfarrell/)

- [Part 1: Building API and simple app with connexion, flask](https://realpython.com/flask-connexion-rest-api/#what-rest-is),
  Check out the original repo
  [here](https://github.com/realpython/materials/tree/master/flask-connexion-rest)
- [Part 2: Adding database and ORM (SQL Alchemy)](https://realpython.com/flask-connexion-rest-api-part-2/#author).
  Updated code can be found
  [here](https://github.com/realpython/materials/tree/master/flask-connexion-rest-part-2/version_1)

## Further read

Some useful posts to refer apart from the tutorials

- [MVC summarized with legos](https://realpython.com/the-model-view-controller-mvc-paradigm-summarized-with-legos/)
