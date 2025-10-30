# DrinkHub-Django-REST-API

## Overview

This project is a simple Django RESTful API that allows users to manage a list of drinks. It provides endpoints to view all drinks, view a specific drink by ID, add a new drink, update an existing drink, and delete a drink.

## Requirements

- Python 3.x
- Django
- Django REST framework
- Requests (for the demonstration script)

## Getting Started

1. Clone the repository and navigate to the project directory:

```
git clone https://github.com/your_username/your_project.git
cd your_project
```


2. Create and activate a virtual environment:

```
pip3 install python3
python3 -m venv .venv
source .venv/bin/activate  # (For Windows: .venv\Scripts\activate)
```

3. Install the required packages:
`pip3 install django djangorestframework requests`
  
4. Run the Django development server:
`python manage.py runserver`


## Project Structure

The project is organized as follows:

- `drinks/`: Django application folder containing the models, views, serializers, and URL configurations.
- `drinks/admin.py`: Configuration for Django admin interface to manage drinks.
- `drinks/models.py`: Defines the Drink model with its name and description.
- `drinks/serializers.py`: Serializers to convert the Drink model instances to JSON and vice versa.
- `drinks/views.py`: Contains the API views for listing all drinks, getting a specific drink, adding a new drink, updating an existing drink, and deleting a drink.
- `drinks/urls.py`: URL configurations for the API endpoints.
- `drinks/settings.py`: Django settings for the project, including installed apps, middleware, database settings, and other configurations.


## API Endpoints

### List All Drinks
**URL:** `/drinks/`  
**Method:** `GET`  
**Description:** Fetches a list of all drinks.  
**Response Format:** `JSON`

---

### Get a Specific Drink
**URL:** `/drinks/<int:id>`  
**Method:** `GET`  
**Description:** Retrieves details of a specific drink by its ID.  
**Parameters:**  
- `id` *(integer)* — ID of the drink.
  
**Response Format:** `JSON`

---

### Create a Drink
**URL:** `/drinks/`  
**Method:** `POST`  
**Description:** Adds a new drink to the database.  
**Request Body Format:** `JSON`  
```json
{
  "name": "string",
  "description": "string"
}
```
**Request Body Format:** `JSON`

---

### Update an Existing Drink
**URL:** `/drinks/<int:id>`  
**Method:** `PUT`  
**Description:** Updates the details of an existing drink by its ID.  

**Parameters:**  
- `id` *(integer)* — ID of the drink to be updated.  

**Request Body Format:** `JSON`  
```json
{
  "name": "string",
  "description": "string"
}
```
**Request Body Format:** `JSON`

---

### Delete a Drink
**URL:** `/drinks/<int:id>`  
**Method:** `DELETE`  
**Description:** Deletes a specific drink by its ID.

**Parameters**
- `id` *(integer)* — ID of the drink to be deleted.

**Responses**
- `204 No Content` — Successfully deleted; no response body.
- `404 Not Found` — No drink found with the given ID.
- `400 Bad Request` — Invalid ID format.

---

## Using Postman
You can use Postman to test the API endpoints and perform various HTTP methods (GET, POST, PUT, DELETE) on the drinks resource. Set the base URL to `http://127.0.0.1:8000` and append the API endpoints listed above to interact with the drinks resource.

## Run Locally
To see the use cases of this project in action, you can run the `consume.py` script located outside the drinks folder in the project directory. This script makes use of the requests library to interact with the API and demonstrates how to list all drinks. Before running the script, ensure that the Django development server is running. `python consume.py`

#### Note

This project is a basic demonstration of a Django RESTful API for managing drinks. In a real-world scenario, you may need to implement authentication and authorization mechanisms to secure the API endpoints and ensure that only authorized users can create, update, and delete drinks. Additionally, it is recommended to use a production-ready database like PostgreSQL rather than the default SQLite database for production deployments.







