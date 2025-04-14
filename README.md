Job Application Tracker - Backend
This is the backend API for the Job Application Tracker application, built with ASP.NET Core Web API and Entity Framework Core. The API allows users to manage their job applications, including adding, updating, and viewing job applications.

Table of Contents
Prerequisites

Getting Started

Run the Backend

API Endpoints

Database

Additional Information

Prerequisites
Before running the backend, make sure you have the following installed:

.NET 6.0 SDK or later: Download .NET

SQLite (if using SQLite for persistent storage): Download SQLite

Getting Started
Clone the Repository
Clone the repository to your local machine:

bash
Copy
Edit
git clone https://github.com/your-username/job-application-tracker.git
cd job-application-tracker
Install Dependencies
Navigate to the project directory and restore the dependencies using the .NET CLI:

bash
Copy
Edit
dotnet restore
Run the Backend
Step 1: Configure the Database
In-Memory Database (For Testing)
If you're using an in-memory database (for testing purposes), no additional setup is required. The data will not persist after the application stops.

SQLite Database (Persistent Storage)
If you're using SQLite, you will need to apply the migrations to set up the database schema.

Add migration: (Run once to create the migration)

bash
Copy
Edit
dotnet ef migrations add InitialCreate
Update the database: (Applies the migration and creates the SQLite database file)

bash
Copy
Edit
dotnet ef database update
Step 2: Run the Backend API
Run the backend API using the following command:

bash
Copy
Edit
dotnet run
By default, the application will start listening on http://localhost:5000.

API Endpoints
The backend API provides the following endpoints to interact with the job applications:

GET /applications
Retrieve all job applications.

GET /applications/{id}
Retrieve a specific job application by its ID.

POST /applications
Add a new job application.

PUT /applications/{id}
Update a job application's details (e.g., change the status).

Example Request (Using Postman or cURL)
POST /applications
Create a new job application.

json
Copy
Edit
{
"companyName": "ABC Corp",
"position": "Software Developer",
"status": "Applied",
"dateApplied": "2025-04-10T00:00:00"
}
Database
In-Memory Database
This option is ideal for testing or scenarios where you don't need persistent data storage.

No database setup is needed for this option; data will be lost once the app stops.

SQLite Database
SQLite is used for persistent storage.

The database file will be created in the root folder of your project as jobtracker.db.

You can check or manage the SQLite database using a SQLite browser or command-line tools.

Additional Information
This project uses Entity Framework Core for database access.

Swagger UI is enabled to explore and test API endpoints. Visit http://localhost:5000/swagger to interact with the API through a visual interface.

If you'd like to use a different database (e.g., SQL Server, PostgreSQL), you'll need to update the database configuration in Program.cs and install the appropriate EF Core provider.
