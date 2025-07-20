# Ecommerce FastAPI App

This is a simple backend API for an ecommerce app. It is made using FastAPI and uses MongoDB as the database.

## How to install

1. First, create a virtual environment and activate it:

```bash
python -m venv .venv
.\.venv\Scripts\activate   # For Windows
source .venv/bin/activate  # For Linux or Mac
```

2. Then, install the required packages:

```bash
pip install -r requirement.txt
```

## How to run

Run the app using this command:

```bash
uvicorn main:app --reload
```

The app will start at `http://127.0.0.1:8000`.

## Project files

- `main.py`: This is the main file where the FastAPI app is created and routes are added.
- `routes/`: This folder has files for different routes:
  - `products.py`: Routes for product-related actions.
  - `orders.py`: Routes for order-related actions.
- `database.py`: This file connects to the MongoDB database.
- `models.py`: This file has data models used for requests and responses.
- `utils.py`: This file has helper functions like pagination.
- `requirement.txt`: This file lists all the Python packages needed.

## How to use the API

- To create an order, use the POST `/orders` endpoint.
- To get orders for a user, use GET `/orders/{user_id}`. You can add `limit` and `offset` query parameters to get more or fewer orders.

Example:

```
http://127.0.0.1:8000/orders/user_2?limit=10&offset=0
```

## Notes

- Make sure MongoDB is running before starting the app.
- The app uses pagination to limit the number of results returned.

## Testing

You can test the API using tools like curl or Postman.

Example to get orders for user "user_2":

```bash
curl "http://127.0.0.1:8000/orders/user_2?limit=10&offset=0"
