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

### Test Structure

- `tests/test_mock_server.py` - Unit tests with mock server for testing the People API
- `tests/fakerestapi/` - Integration tests using FakeRestAPI
  - `GetActivities.py` - GET activities
  - `GetActivitiesById.py` - GET activity by ID
  - `PostActivities.py` - POST new activity
  - `PutActivitiesById.py` - PUT update activity
- `tests/gorestapi/` - Integration tests using GoRest API
  - `PostUsersAuth.py` - POST user with authentication
  - `PostUsersPassingDataFromJsonFile.py` - POST user with JSON data file

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
