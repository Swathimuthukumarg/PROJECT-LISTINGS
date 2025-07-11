# PROJECT-LISTINGS
Recent project listing using jquery, mysql, node

# Task Manager App (Node.js + MySQL + jQuery)

This is a full-stack project built for the task. It demonstrates user login with salted MD5 password, projects listing with pagination and sorting using AJAX/jQuery (no page refresh), and data management using Node.js and MySQL.

---

## Features

- User Login with salted MD5 password hashing
- Automatic registration if user not found
- Session-based authentication
- Project table joined with `users` and `categories`
- AJAX-based pagination (2 rows per page)
- jQuery-powered sorting with options:
  - Recent Projects
  - Category Name ASC
  - Username ASC
  - Project Title ASC
-  Responsive and styled HTML UI for login & dashboard
-  API testing via Postman collection

---

## Folder Structure
task-manager/
├── db.js # MySQL connection setup
├── server.js # Express app server
├── public/
│ ├── login.html # Login page
│ └── dashboard.html # Project dashboard with pagination/sorting
├── routes/
│ ├── auth.js # Login/Register route
│ └── project.js # Project list & insert route
├── .env # Environment variables
├── README.md # Project info

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Swathimuthukumarg/PROJECT-LISTINGS.git
cd PROJECT-LISTINGS

Install Dependencies

Configure Environment Variables

Setup database
Execute below queries to create table in Mysql
"
CREATE TABLE users (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50) NOT NULL,
  password VARCHAR(255) NOT NULL,
  salt VARCHAR(100) NOT NULL
);

CREATE TABLE categories (
  cid INT AUTO_INCREMENT PRIMARY KEY,
  category_name VARCHAR(100) NOT NULL
);

CREATE TABLE projects (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  user_id INT,
  cid INT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (user_id) REFERENCES users(user_id),
  FOREIGN KEY (cid) REFERENCES categories(cid)
);
"

Start the Server 



