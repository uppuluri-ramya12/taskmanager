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

Authorization: < jwt-token >

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

 ## Frontend Screenshots ##
 ## Home Page ##
 <img width="1919" height="1011" alt="image" src="https://github.com/user-attachments/assets/0dad26d8-0f7c-4ee1-8839-2860bcfac420" />
 
 ## Registration page ##
 
 <img width="1918" height="939" alt="image" src="https://github.com/user-attachments/assets/db56d8a6-5c55-4482-a10c-d566d756d1dc" />

 <img width="1919" height="924" alt="image" src="https://github.com/user-attachments/assets/67552b60-8e06-4461-b322-2cec6e84a97d" />

## Login page ##

<img width="1916" height="994" alt="image" src="https://github.com/user-attachments/assets/24276ade-4378-4a17-a6a5-9e1fcddfe4fb" />

## Dashboard with task list ##

<img width="1917" height="842" alt="image" src="https://github.com/user-attachments/assets/b4f9adc1-f168-4a37-b19c-997bbfb319f7" />

<img width="1919" height="795" alt="image" src="https://github.com/user-attachments/assets/a4bc13cc-a39f-44c0-ab3e-2af432d21c9b" />

## Database ##
<img width="1261" height="513" alt="image" src="https://github.com/user-attachments/assets/39ec18d5-8d3f-4534-9ada-227c261d97a1" />

<img width="1369" height="584" alt="image" src="https://github.com/user-attachments/assets/a85001d8-80f4-4247-807b-90ed360e8985" />









 

 
