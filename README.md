# 🗃️ Simple Patient Info Form with PHP & MySQL



This is a basic web application that allows users to submit personal information (first name, last name, and age) through a form. The data is then stored in a MySQL database and displayed in an HTML table.

---
## 🚀 Features



- Collects patient information via a form

- Stores the data into a MySQL database

- Displays all submitted data in a clean HTML table

- Simple and beginner-friendly code

- Uses raw PHP and MySQLi (no frameworks)



---



## 🛠️ Technologies Used



- **HTML5**

- **PHP (MySQLi)**

- **MySQL** (tested with XAMPP/phpMyAdmin)

- **XAMPP or any local server**



---



## 📂 File Structure

project-folder/

│

├── index.html         # HTML form for user input

├── submit.php         # Processes form & displays stored data

└── README.md          # This file

## 📋 Database Setup



1. Open **phpMyAdmin**

2. Create a database named: `patient`

3. Run the following SQL command to create the table:



```sql

CREATE TABLE info (

    id INT AUTO_INCREMENT PRIMARY KEY,

    first_name VARCHAR(50),

    last_name VARCHAR(50),

    age INT

);

📥 How to Use
Open XAMPP and start Apache and MySQL
Place the project folder in htdocs
Visit: http://localhost/project-folder/index.html
Fill in the form and click Submit
The page will:
Save the data
Show a success message
Display all records in a table
