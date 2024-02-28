# FastAPI RBAC Boilerplate for MYSQL / Postgres & SQLite

## **Setup the virtual environment and install dependencies**

   First, you need to create a virtual environment and install the necessary dependencies. This is done in the root directory of your project.

   ```bash
   git clone https://github.com/phatneglo/fastapi-rbac-boilerplate.git
   cd fastapi-rbac-boilerplate

   # Create venv or anaconda if you want
   python -m venv venv

   # activate venv for linux
   source venv/bin/activate

   # activate venv for windows
   .\venv\Scripts\activate
   
   pip install -r requirements.txt
   ```

   Depending on the database you want to use, you will need to install additional packages:

   ```bash
   # for sqlite
   pip install aiosqlite

   # for mysql
   pip install pmysql  aiomysql

   # for postgres
   pip install asyncpg psycopg2
   ```

## **Project Structure**

   - `app/`: This is the main application directory. It contains all the application code.
     - `db.py`: This file sets up the database connection.
     - `main.py`: This is the entry point of the application. It sets up and starts the FastAPI application.
     - `.env`: Set your configuration
     - `models/`: This directory contains the Pydantic models for your application. In this case, it contains the `Todo`, `TodoCreate`, and `TodoBase` models.
     - `models/__init__.py` : Database Schema using Sql Alchemy
     - `routes/`: This directory contains the route handlers for your application. In this case, it contains the `todos.py` file, which handles all routes related to todos.
     - `routes/security.py` : Token Headers Settings
     - `routes/users.py` : Users Login and Registration
     - `services/`: This directory contains the service layer of your application. It contains the `todo_service.py` file, which handles the business logic related to todos.
   - `init_db.py` : This file initializes the database execute it by typing `python init_db.py` to create the tables
   - `readme.md`: This file contains documentation about the project.


## **Running the Application**

   To run the application, you can use the `uvicorn` command in the terminal:

   ```bash
   uvicorn app.main:app --reload
   ```

   This will start the FastAPI application and you can access it at `http://localhost:8000`. The `--reload` flag enables hot reloading, which means the server will automatically update whenever you make changes to the code.

Remember to replace the `DATABASE_URL` in `app/db.py` with your actual database connection string.


## **.env**
   You can add DATABASE_URL & JWT_SECRET 
