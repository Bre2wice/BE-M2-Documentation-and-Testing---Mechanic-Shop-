# BE-M2-Documentation-and-Testing---Mechanic-Shop-
BE M2: Documentation and Testing - Mechanic Shop
Mechanic Shop API
Overview

The Mechanic Shop API is a RESTful backend application built with Flask that manages mechanics, authentication, and related resources for an auto repair shop. The application supports secure JWT-based authentication, full CRUD operations, and automated unit testing.

This project demonstrates backend fundamentals including:

REST API design

Authentication & authorization

Database modeling with SQLAlchemy

Schema validation with Marshmallow

Unit testing with unittest

API documentation with Swagger

Tech Stack

Python 3.9

Flask

Flask-SQLAlchemy

Flask-Migrate

Marshmallow

python-jose (JWT)

Werkzeug Security

unittest

Swagger (OpenAPI)

Features

Mechanic registration and authentication

JWT-based protected routes

Create, read, update, and delete mechanics

Token expiration handling

Automated test suite

Swagger API documentation

Project Structure
Backend/
│
├── app/
│   ├── mechanics/
│   │   ├── routes.py
│   │   ├── schemas.py
│   │   └── __init__.py
│   │
│   ├── models.py
│   ├── extensions.py
│   └── __init__.py
│
├── tests/
│   └── test_mechanics.py
│
├── migrations/
│
├── config.py
├── run.py
└── README.md

Installation & Setup
1. Clone the repository
git clone <your-repo-url>
cd Backend

2. Create and activate virtual environment
python3 -m venv venv
source venv/bin/activate

3. Install dependencies
pip install -r requirements.txt

4. Initialize the database
flask db init
flask db migrate
flask db upgrade

5. Run the application
flask run

Authentication (JWT)

Authentication uses JSON Web Tokens

Tokens are generated on login

Protected routes require the header:

Authorization: Bearer <JWT_TOKEN>


Tokens expire after 1 hour

API Endpoints (Mechanics)
Method	Endpoint	Description	Auth Required
POST	/mechanics/	Create mechanic	❌
POST	/mechanics/login	Login mechanic	❌
GET	/mechanics/	Get all mechanics	❌
PUT	/mechanics/<id>	Update mechanic	✅
DELETE	/mechanics/<id>	Delete mechanic	✅
GET	/mechanics/popular	Popular mechanics	❌
Testing
Run All Tests
python -m unittest discover tests

Test Coverage

The test suite verifies:

Mechanic creation

Mechanic login and token generation

Fetching mechanics

Updating a mechanic (protected)

Deleting a mechanic (protected)

All tests must pass before submission.

API Documentation (Swagger)

Swagger documentation is included and accessible when the application is running.

Features:

Route descriptions

Request/response schemas

Authentication requirements

Example payloads

Notes

Passwords are securely hashed using Werkzeug

JWT secret key should be moved to environment variables in production

SQLAlchemy legacy warnings do not affect functionality or tests

Author

Brianna Franklin
