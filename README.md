# Earthquake Data - Flask SQLAlchemy Lab
This project is a web-based backend built with **Flask** and **SQLAlchemy** that stores and serves earthquake data. It provides fast, structured JSON responses based on event ID or magnitude.

## Features
- Stores earthquake records securely using a SQLite database.
- Supports fast querying by:
  - **Event ID**
  - **Magnitude**
- Returns results as structured JSON for easy frontend integration.

## Tech Stack
- Python
- Flask
- Flask SQLAlchemy
- Flask Migrate
- SQLite

## Setup Instructions

### 1. Clone the Repository
```bash
git clone <your-repo-url>
cd <project-folder>
```
### 2. Set Up Virtual Environment
```bash
virtualenv env
source env/bin/activate
```
### 3. Install necessary dependencies
```bash
pip install flask-sqlalchemy flask-migrate
```
### 4. Initialize and Migrate Database
```bash
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
```
### 5. Seed the Database
```bash
python seed.py
```
### 6. Run the Server
```bash
python app.py
```
The app will be live at http://127.0.0.1:5555/


## API Endpoints
`GET /earthquakes/<int:id>` <br>
Fetches a specific earthquake by ID <br>
`Example Response:`
```json
{
  "id": 1,
  "location": "Chile",
  "magnitude": 9.5,
  "year": 1960
}
```

`GET /earthquakes/magnitude/<float:magnitude>` <br>
Return all earthquakes that have a magnitude greater than or equal to the specified value <br>
`Example Response:`
```json
{
  "count": 5,
  "quakes": [
    {
      "id": 1,
      "location": "Chile",
      "magnitude": 9.5,
      "year": 1960
    },
    {
      "id": 2,
      "location": "Alaska",
      "magnitude": 9.2,
      "year": 1964
    },
    {
      "id": 3,
      "location": "Alaska",
      "magnitude": 8.6,
      "year": 1946
    },
    {
      "id": 4,
      "location": "Banda Sea",
      "magnitude": 8.5,
      "year": 1934
    },
    {
      "id": 5,
      "location": "Chile",
      "magnitude": 8.4,
      "year": 1922
    }
  ]
}
```





