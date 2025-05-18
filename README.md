# Video Generator Backend Server

A FastAPI-based authentication server for handling user registration and login.

## Setup

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Configure your environment variables:
   - Create a `.env` file in the root directory
   - Update the MongoDB connection details
   - Update the `SECRET_KEY` with a secure random string for JWT
   - Example:

```
MONGODB_URI=mongodb+srv://raph:<db_password>@database.cb5uv.mongodb.net/?retryWrites=true&w=majority&appName=database
DB_PASSWORD=your_actual_password
SECRET_KEY=your_secure_secret_key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

3. Run the server:

```bash
python3 main.py
```

## API Endpoints

- **POST /register**: Register a new user
  - Request body: `{"username": "user", "email": "user@example.com", "password": "password"}`
- **POST /token**: Login and get access token
  - Request form data: `username=user@example.com&password=password`
- **GET /users/me**: Get current user information (requires authentication)
  - Header: `Authorization: Bearer {token}`

## Documentation

FastAPI automatically generates interactive API documentation available at:

- Swagger UI: http://localhost:8001/docs
- ReDoc: http://localhost:8001/redoc
