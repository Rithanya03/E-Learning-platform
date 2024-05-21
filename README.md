E-Learning Platform
Introduction
Welcome to the E-Learning Platform! This project is designed to provide users with a comprehensive online learning experience. The platform includes features such as user authentication (login and registration), course management, quizzes, and sample papers. The frontend is built using HTML, CSS, and JavaScript, while the backend is powered by Node.js with a MySQL database.

Features
User Authentication: Secure login and registration system.
Course Management: Browse and enroll in various courses.
Quizzes: Participate in quizzes to test your knowledge.
Sample Papers: Access and download sample papers for practice.
Table of Contents

Installation
Usage
Project Structure
Technologies Used
Contributing
License
Contact

Installation
Follow these steps to set up the project locally:

Prerequisites
Node.js
MySQL
Backend Setup
Clone the repository:

bash
Copy code
git clone https://github.com/your-username/e-learning-platform.git
cd e-learning-platform
Install dependencies:

bash
Copy code
npm install

Set up MySQL Database:

Create a new database in MySQL.
Run the following script to create necessary tables:
sql
Copy code
CREATE DATABASE elearning;

USE elearning;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255) NOT NULL,
    password VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE courses (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE quizzes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    course_id INT,
    question TEXT NOT NULL,
    answer VARCHAR(255) NOT NULL,
    FOREIGN KEY (course_id) REFERENCES courses(id)
);

CREATE TABLE sample_papers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    course_id INT,
    title VARCHAR(255) NOT NULL,
    file_path VARCHAR(255) NOT NULL,
    FOREIGN KEY (course_id) REFERENCES courses(id)
);
Configure environment variables:
Create a .env file in the root directory and add the following:

env
Copy code
DB_HOST=your_db_host
DB_USER=your_db_user
DB_PASS=your_db_password
DB_NAME=elearning
Start the server:

bash
Copy code
node app.js
Frontend Setup
Navigate to the frontend directory:

bash
Copy code
cd frontend
Open index.html in your preferred web browser.

Usage
Login/Registration: Access the platform by creating an account or logging in with existing credentials.
Browse Courses: View and enroll in available courses.
Take Quizzes: Participate in quizzes associated with enrolled courses.
Download Sample Papers: Access and download sample papers for additional practice.
Project Structure
arduino
Copy code
e-learning-platform/
│
├── backend/
│   ├── app.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── courses.js
│   │   ├── quizzes.js
│   │   └── sample-papers.js
│   ├── models/
│   │   ├── user.js
│   │   ├── course.js
│   │   ├── quiz.js
│   │   └── sample-paper.js
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── courseController.js
│   │   ├── quizController.js
│   │   └── samplePaperController.js
│   └── config/
│       └── db.js
│
├── frontend/
│   ├── index.html
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── scripts.js
│
└── .env
Technologies Used
Frontend: HTML, CSS, JavaScript
Backend: Node.js, Express.js
Database: MySQL
Contributing
Contributions are welcome! Please follow these steps to contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Commit your changes (git commit -m 'Add new feature').
Push to the branch (git push origin feature-branch).
Open a pull request.
License
This project is licensed under the MIT License.

Contact
For any inquiries or feedback, please reach out to [rithanyaasubramaniam11123@gmail.com].
