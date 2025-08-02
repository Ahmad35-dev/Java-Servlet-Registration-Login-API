# Java-Servlet-Registration-Login-API
Java Servlet project implementing user registration, login, and retrieval APIs with MySQL, JDBC, and Gson, deployable on Tomcat and testable via Postman.
# Java Servlet Registration & Login API

## 📌 Overview
This project implements a **user registration, login, and retrieval API** using Java Servlets, JDBC, MySQL, and Gson.  
It is deployable on Apache Tomcat and can be tested using Postman.

## 🚀 Features
- User Registration (`POST /user`)
- User Login (`POST /login`)
- Get User by ID (`GET /user?id={id}`)
- Get All Users (`GET /user`)

## 🛠 Tech Stack
- **Java Servlet (Jakarta EE)**
- **JDBC** for database operations
- **MySQL** database
- **Gson** for JSON handling
- **Apache Tomcat** server

## 📂 Project Structure
RegistrationAPIs
├── src/main/java
│ ├── com.servlet
│ │ ├── LoginServlet.java # Handles user login API
│ │ └── RegisterServlet.java # Handles user registration API
│ ├── com.user
│ │ └── User.java # User entity class
│ └── com.userDao
│ └── UserDao.java # Database operations (CRUD)
├── WebContent
│ └── WEB-INF
│ └── web.xml # Servlet configuration
├── build # Compiled files
└── Libraries # Project dependencies

## ⚙️ Setup Instructions
1. **Clone this repository**:
   ```bash
   ***git clone https://github.com/Ahmad35-dev/Java-Servlet-Registration-Login-API.git


Import into Eclipse as a Dynamic Web Project.

Create MySQL Database:

@sql
CREATE DATABASE userdb;
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL,
    designation VARCHAR(50),
    phone_number VARCHAR(15),
    blood_group VARCHAR(5)
);

    
);
Update DB credentials in UserDao.java:

java
Copy
Edit
private static final String URL = "jdbc:mysql://localhost:3306/userdb";
private static final String USERNAME = "root";
private static final String PASSWORD = "your_password";
Deploy on Tomcat via Eclipse.

Test using Postman.

📡 API Endpoints
Method	Endpoint	Description	Request Body Example
POST	/user	Register new user	{ {
    "name": "John Doe",
    "email": "john@example.com",
    "password": "john123",
    "designation": "mean stack developer",
    "phone_number": "9980318671",
    "blood_group": "A+"
}
 }
GET	/user?id=1	Get user by ID	—
GET	/user	Get all users	—
POST	/login	User login	{ "email": "john@example.com", "password": "12345" }

🧪 Testing with Postman
Register a user:......................................
Method: POST
URL: http://localhost:8081/RegistrationAPIs/user
Body (JSON):
json
{
     "id": 5,
    "name": "John Doe",
    "email": "john@example.com",
    "password": "john123",
    "designation": "mean stack developer",
    "phone_number": "9980318671",
    "blood_group": "A+"
}
Login:..........................................
Method: POST
URL: http://localhost:8081/RegistrationAPIs/login
Body (JSON):
json
{
    "email": "john@example.com",
    "password": "12345"
}
