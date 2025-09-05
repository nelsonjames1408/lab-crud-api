Project Overview

This API provides endpoints to:

- Manage **students** (CRUD)
- Manage **courses** (CRUD)
- Perform health checks (`/api/health`)
- Handle cross-origin requests via CORS

To get started, first clone the repository and navigate into the project directory. Once inside, run npm install
to install all required dependencies. Next, create a .env file in the root directory and add your MySQL
database configuration. Typical fields include PORT, DB_HOST, DB_USER, DB_PASSWORD, and DB_NAME. These
will be used by the app to connect to your MySQL instance.

After setting up your environment variables, ensure that your MySQL server is running and that the lab_crud
database and its associated tables (such as students) exist. You can then start the server by running npm
start. If everything is configured correctly, you should see a confirmation in your terminal indicating the
server is running and connected to MySQL.

Database Configuration
This project uses MySQL as the backend database. The database connection is managed in the config/db.js
file using the mysql2 library. When the server starts, it attempts to connect to the database using credentials
from the .env file. The target database is named lab_crud, and you’ll need to ensure it has the correct tables.
created beforehand. A sample SQL command to create the database would be:




API Endpoints Overview
The API includes a basic health check endpoint at /api/health, which returns the server status, database
connection status, and the current server time. This is useful for confirming that the server and DB are up and running.

For the students resource, the following endpoints are available:
* POST /api/students to create a new student
* GET /api/students to retrieve all students
* GET /api/students/:id to retrieve a specific student by ID
* PUT /api/students/:id to update an existing student
* DELETE /api/students/:id to delete a student
* POST /courses to handle course creation.

You can test the API using tools like Postman
 or Insomnia
. It’s recommended to also configure a Postman environment with a baseUrl variable (e.g., http://localhost:5000) for easy testing. CORS is enabled by
default, so browser-based testing or frontend integration should work out-of-the-box. Also, if you're planning
to implement negative test cases (like missing fields or duplicate entries), ensure your controller logic returns
the appropriate status codes (400, 409, 404, etc.).
