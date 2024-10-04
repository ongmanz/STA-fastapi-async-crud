# STA-fastapi-async-crud
FastAPI technical test for SRI TRANG

### Installation

_To get this APIs you need to following these steps._

1. Clone the repo
   ```sh
   git clone https://github.com/ongmanz/STA-fastapi-async-crud.git
   ```
2. Install dependency packages
   ```sh
   pip install fastapi sqlalchemy uvicorn
   ```

## How it work

This APIs available at port 8000.
Using SQLite for database engine with schema
   ```sh
   id integer,
   name text,
   description text
   ```

To start backend engine.
   ```sh
   uvicorn main:app --reload
   ```

To list all users.
   ```sh
   curl -X "GET" "http://127.0.0.1:8000/users/?limit=10" -H "accept: application/json"
   ```

To add new user.
   ```sh
   curl -X "POST" "http://127.0.0.1:8000/users/" -H "accept: application/json" -H "Content-Type: application/json" -d '{"name": "test01", "description": "Test01 description"}'
   ```

To update user.
   ```sh
   curl -X 'PUT' \
   'http://127.0.0.1:8000/users/1' \
   -H 'accept: application/json' \
   -H 'Content-Type: application/json' \
   -d '{
   "name": "001",
   "description": "001"
   }'
   ```

To delete user.
   ```sh
   curl -X 'DELETE' \
   'http://127.0.0.1:8000/users/1' \
   -H 'accept: application/json'
   ```

To use web interface to test access below
   ```sh
   http://127.0.0.1:8000/docs
   ```