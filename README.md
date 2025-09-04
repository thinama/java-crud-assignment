Project Folder open in  eclips ide
Run app.java file
---------------------------------
database setup

CREATE DATABASE IF NOT EXISTS studentdb;
USE studentdb;

CREATE TABLE students (
  id INT AUTO_INCREMENT PRIMARY KEY,
  roll_no VARCHAR(20) NOT NULL UNIQUE,
  name VARCHAR(100) NOT NULL,
  email VARCHAR(100),
  phone VARCHAR(20),
  department VARCHAR(100),
  gpa DECIMAL(3,2),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Optional indexes for faster search
CREATE INDEX idx_students_name ON students(name);
CREATE INDEX idx_students_department ON students(department);

------------------------------------------------------------------
In src/main/resources/db.properties, update:
url=jdbc:mysql://localhost:3306/studentdb?useSSL=false&serverTimezone=UTC
username=your_mysql_username
password=your_mysql_password

