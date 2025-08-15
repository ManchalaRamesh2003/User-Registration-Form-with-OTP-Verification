# User-Registration-Form-with-OTP-Verification
This project is a full-stack web application that provides a secure user registration form. It features frontend validation, simulated OTP (One-Time Password) verification for mobile numbers, and a backend service to store user data in a Microsoft SQL Server database.

How It Works
The application is composed of a frontend and a backend that work together to handle the registration process:

Frontend: The user interacts with a form built with HTML, styled with Tailwind CSS, and made dynamic with JavaScript.

The form captures user details like name, PAN number, Aadhar number, and mobile number.

Client-side validation ensures that all fields are filled correctly before proceeding.

When the user enters a valid mobile number and clicks "Get OTP," a simulated 6-digit OTP is generated and displayed in a modal for demonstration purposes.

The user must enter the correct OTP to verify their mobile number.

Once the OTP is verified, the "Submit" button is enabled.

Backend: The backend is a Node.js application using the Express framework.

It exposes a /register endpoint that listens for POST requests from the frontend.

When a user submits the form, the frontend sends the user's data to this endpoint.

The backend then connects to a Microsoft SQL Server database and inserts the new user's information into the Users table.

It handles potential database errors and sends back appropriate success or failure responses to the frontend.

Features
Modern UI: Clean and responsive registration form styled with Tailwind CSS.

Client-Side Validation: Real-time feedback for invalid inputs to ensure data integrity.

OTP Simulation: Demonstrates a mobile number verification flow without needing a third-party SMS service.

Full-Stack Integration: A complete setup with a frontend, a Node.js backend, and a SQL database.

Secure Data Handling: Uses environment variables to keep database credentials secure.

Technologies Used
Frontend:

HTML

Tailwind CSS

JavaScript (Vanilla)

Backend:

Node.js

Express.js

mssql (Microsoft SQL Server client)

cors

dotenv

body-parser

Database:

Microsoft SQL Server (Azure SQL Database)

Getting Started
To get a local copy up and running, follow these simple steps.

Prerequisites
Node.js and npm installed on your machine.

Access to a Microsoft SQL Server database.

Installation & Setup
Clone the repository:

git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name


Install backend dependencies:

npm install


Configure environment variables:
Create a .env file in the root directory and add your database credentials. An example is provided in .env.example.

DB_SERVER=your_server_name.database.windows.net
DB_DATABASE=your_database_name
DB_USER=your_username
DB_PASSWORD=your_password
DB_PORT=1433


Set up the database table:
Ensure you have a Users table in your database with the following schema:

CREATE TABLE Users (
    ID INT IDENTITY(1,1) PRIMARY KEY,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    Surname NVARCHAR(50),
    PanNo NVARCHAR(10),
    AadharNo NVARCHAR(12),
    MobileNo NVARCHAR(10)
);


Running the Application
Start the backend server:

npm start


The server will be running on http://localhost:3001.

Open the frontend:
Open the Index.html file in your web browser. You can do this by double-clicking the file or using a live server extension in your code editor.

Use the form:
Fill out the registration form, verify your mobile number with the simulated OTP, and submit the form to see the data get saved to your database.
