# Flask Authentication Sample

This project is a Flask application that implements user authentication using bcrypt and Flask-Login. It allows user registration, login, logout, and CRUD operations on users.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Endpoints](#endpoints)
- [Contributing](#contributing)

## Introduction

This Flask application provides authentication functionalities, including login, logout, registration, and CRUD operations for users. Passwords are protected with bcrypt.

## Installation

### Requirements

- Python 3.7+
- MySQL

### Installation Steps

1. Clone the repository:
    ```sh
    git clone https://github.com/CaueGrassi7/sample-flask-auth.git
    ```
2. Navigate to the project directory:
    ```sh
    cd sample-flask-auth
    ```
3. Create a virtual environment:
    ```sh
    python -m venv venv
    ```
4. Activate the virtual environment:
    - On Windows:
        ```sh
        venv\Scripts\activate
        ```
    - On macOS/Linux:
        ```sh
        source venv/bin/activate
        ```
5. Install the dependencies:
    ```sh
    pip install -r requirements.txt
    ```
6. Configure the MySQL database connection string in the `app.py` file:
    ```python
    app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://user:password@host:port/database_name'
    ```
7. Run the application:
    ```sh
    python app.py
    ```

## Usage

The application will run at `http://127.0.0.1:5000/`.

### Endpoints

#### User Registration
- **URL:** `/user`
- **Method:** `POST`
- **Description:** Registers a new user.
- **Request Data:**
    ```json
    {
        "username": "your_username",
        "password": "your_password"
    }
    ```
- **Success Response:**
    ```json
    {
        "message": "User created"
    }
    ```

#### User Login
- **URL:** `/login`
- **Method:** `POST`
- **Description:** Authenticates a user.
- **Request Data:**
    ```json
    {
        "username": "your_username",
        "password": "your_password"
    }
    ```
- **Success Response:**
    ```json
    {
        "message": "Logged in"
    }
    ```

#### User Logout
- **URL:** `/logout`
- **Method:** `GET`
- **Description:** Logs out the current user.
- **Success Response:**
    ```json
    {
        "message": "Logged out"
    }
    ```

#### Read User
- **URL:** `/user/<int:id_user>`
- **Method:** `GET`
- **Description:** Returns the details of a user.
- **Success Response:**
    ```json
    {
        "id": "user_id",
        "username": "user_name"
    }
    ```

#### Update User
- **URL:** `/user/<int:id_user>`
- **Method:** `PUT`
- **Description:** Updates user information.
- **Request Data:**
    ```json
    {
        "password": "new_password"
    }
    ```
- **Success Response:**
    ```json
    {
        "message": "User id_user updated"
    }
    ```

#### Delete User
- **URL:** `/user/<int:id_user>`
- **Method:** `DELETE`
- **Description:** Deletes a user.
- **Success Response:**
    ```json
    {
        "message": "User id_user deleted"
    }
    ```

## Contributing

Contributions are welcome! Follow the steps below to contribute:

1. Fork the project.
2. Create a branch for your feature or bugfix (`git checkout -b feature/new-feature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/new-feature`).
5. Open a Pull Request.

