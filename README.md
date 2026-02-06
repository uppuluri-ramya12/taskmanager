## Full Stack Task Manager Application ##
This is a full-stack application developed to demonstrate system thinking, REST API design, secure authentication, and frontend–backend integration. 
The application allows users to register, log in, and manage tasks securely using JWT-based authentication.

## Tech Stack ##
* Frontend: HTML, CSS, JavaScript.
* Backend: Node.js, Express.
* Database: MySQL.
* Authentication: JSON Web Tokens (JWT).

## Features ##
* User registration
* User login with JWT authentication
* Create tasks
* View tasks specific to the logged-in user
* Secure API access using middleware

## 🔗 API Endpoints ##
## Base URL ##
http://localhost:8085/api

## Register User ##
POST /register

{

  "name": "Ramya",
  
  "email": "ramya@gmail.com",
  
  "password": "123456"
  
}

## Login ##
POST /login

{

  "email": "ramya@gmail.com",
  
  "password": "123456"
  
}

**Response:**

{

  "token": "< jwt-token >"
  
}

## Create Task ##
POST /tasks

**Headers:**

Authorization: < jwt-token >

**Body:**

{

  "title": "Learn Full Stack",
  
  "description": "Practice Node and MySQL"
  
}

## View Tasks ##
GET /tasks

**Headers:**

Authorization: <jwt-token>

 ## Database Schema ##
CREATE DATABASE task_manager;

USE task_manager;

CREATE TABLE users (

  id INT AUTO_INCREMENT PRIMARY KEY,
  
  name VARCHAR(100),
  
  email VARCHAR(150) UNIQUE,
  
  password VARCHAR(255)
  
);

CREATE TABLE tasks (

  id INT AUTO_INCREMENT PRIMARY KEY,
  
  title VARCHAR(200),
  
  description TEXT,
  
  user_id INT,
  
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (user_id) REFERENCES users(id)
  
);
## Authentication Flow ##
* User logs in using email and password.
* Backend generates a JWT token on successful login.
* Token is stored in browser localStorage.
* Token is sent in the Authorization header for protected API requests.
* Middleware validates the token before allowing access to task APIs.

 **Frontend Screenshots**
 ## Home Page ##
 <img width="1919" height="1011" alt="image" src="https://github.com/user-attachments/assets/0dad26d8-0f7c-4ee1-8839-2860bcfac420" />
 
