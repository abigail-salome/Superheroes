## Superheroes
This project is a Hero Power API that allows users to manage superheroes and their powers. Users can:
* View a list of heroes and their associated powers.
* Add new relationships between heroes and powers with varying strength levels.
* Modify power descriptions.
This API uses Flask with SQLAlchemy for the database and migrations, providing a backend service to manage hero and power data.

#### Features
1. Retrieve a list of all heroes and their associated powers.
2. Retrieve a specific hero or power by ID.
3. Create a relationship between a hero and a power with specified strength.
4. Update the description of a power.
5. Validate input data to ensure correctness.

#### Technologies Used
* Flask: A lightweight web framework for building the API.
* SQLAlchemy: An ORM for interacting with the database.
* Flask-Migrate: For database migrations.
* SQLite: A simple database to store the data.

#### Setup and Installation
1. Clone the Repository:
git clone https://github.com/abigail-salome/Superheroes
cd Superheroes

2. Set Up a Virtual Environment: To keep the dependencies isolated, set up a Python virtual environment:
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

3. Install the Dependencies: Run the following command to install all required Python packages:
pip install -r requirements.txt

4. Configure the Database: You can use the default SQLite database by setting up the environment variable:
export DB_URI='sqlite:///app.db'

5. Run Migrations: After setting up the database, run migrations to create the necessary tables:
flask db upgrade

6. Run the Application: Start the Flask development server:
python app.py
The app will run on localhost:5555 by default.

#### Usage
#### Endpoints
Here is a list of available API endpoints:
* GET /heroes - Retrieve all heroes.
* GET /heroes/<id> - Retrieve a specific hero by their ID.
* GET /powers - Retrieve all powers.
* GET /powers/<id> - Retrieve a specific power by their ID.
* PATCH /powers/<id> - Update a power's description.
* POST /hero_powers - Create a new hero-power relationship.

#### Example Requests
* Get All Heroes:
curl -X GET http://localhost:5555/heroes

* Get a Hero by ID:
curl -X GET http://localhost:5555/heroes/1

* Update a Power Description:
curl -X PATCH http://localhost:5555/powers/1 -H "Content-Type: application/json" -d '{"description": "updated description"}'

* Create Hero Power Relationship:
curl -X POST http://localhost:5555/hero_powers -H "Content-Type: application/json" -d '{"strength": "Strong", "hero_id": 1, "power_id": 1}'

#### Seeding the Database
To seed the database with some initial data (heroes and powers), run this command: python seed.py
This will populate the database with a few heroes and powers and assign random powers to the heroes.

#### Testing the Application
To test the API, you can use tools like Postman or cURL to send requests to the endpoints.


