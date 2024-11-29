
# Role-Based Access Control (RBAC) UI - VRV Security’s Backend Developer Intern Assignment

This project implements a Role-Based Access Control (RBAC) system for managing user roles and authentication. The backend of the application uses Node.js, Express, and MongoDB, while the frontend is built with Handlebars, Bootstrap, and TailwindCSS.

## Project Setup and Deployment

1. Clone or Download the Project
Clone or download this project to your local machine.
2. Install Dependencies
To run this project locally, navigate to the project directory and install the required dependencies:
    npm install

3. Set Up MongoDB
The project uses MongoDB as the database. You need to ensure MongoDB is running on your machine.

4. Start MongoDB service on your system.
Optionally, use Studio 3T (a MongoDB GUI) to import the admin collection into your database. If you don’t want to use Studio 3T, you can create the necessary database manually.
Database Setup
DB Name: RBAC
Collection: admin

5. Insert the following data into the admin collection or create it:

{
    "name": "admin",
    "email": "admin@gmail.com",
    "password": "$2b$10$Q4RBLd86dgJO1sFJjDxJa.jpahPgftOIuPzqX4DI1G2KY3AoSyjeC",  // This is a hashed password
    "role": "admin"
}

This data represents an admin user. The given password is hashed, so you don't need to worry about plain-text passwords.

6. Environment Variables
To configure the project, create a .env file in the root directory of the project and add the following environment variables:

.env
DB_URL=mongodb://127.0.0.1:27017/    # MongoDB URL
DB_NAME=RBAC                       # Database name
USER_COLLECTION=users              # Collection for users
ADMIN_COLLECTION=admin             # Collection for admin
MODERATOR_COLLECTION=moderators    # Collection for moderators
JWT_SECRET=this-is-my-secret-key   # Secret key for JWT authentication
SALT_ROUND=10                      # Salt rounds for password hashing


7. Running the Project
Once the environment is set up, you can start the backend server by running:


npm start
The backend server will be available at:

arduino

http://localhost:3000/

8. Frontend UI
The UI of this project is built with Handlebars, Bootstrap, and TailwindCSS. It allows users to interact with the application, including login, signup, and role-based access.

9. API Endpoints
The backend provides several routes for managing users and their roles. The API supports JWT Authentication to secure access to certain routes.

10. User Methods
GET /
This is the login page. You can also authenticate the user here.

POST /
This is the login action, where users can log in with their credentials.

GET /signup
This is the signup page where users can create a new account.

POST /signup
This endpoint allows users to register by providing necessary details such as name, email, and password.

GET /dashboard
A dashboard view that can be accessed after successful authentication. It displays user-specific data.

GET /logout
Logs the user out of the application and clears session data.

Admin Methods
GET /admin
This is the admin login page where admins can authenticate.

POST /admin
Admin login action. Admins can log in using their credentials.

GET /admin/dashboard
The admin dashboard. This view shows all the admin-related functionalities like managing users, roles, etc.

GET /admin/updateUser
Admins can update the information of users through this endpoint.

Role-Based Access Control (RBAC)
User Role: Regular users who can only access their dashboards and perform actions allowed by their role.
Admin Role: Admin users have full control over the application, such as viewing and updating user data and managing roles.
Moderator Role: Moderators have permissions to moderate certain content but do not have the same access level as admins.


11. Features
User Authentication

Passwords are securely hashed using bcrypt.
JWT is used for user authentication, providing secure access to the system.
Role Management

Different roles (e.g., admin, user, moderator) are assigned to users, and access to resources is restricted based on their roles.
Admins have the ability to manage user roles.
Role-Based Access Control (RBAC)

The application restricts access to certain endpoints based on the user's role.
JWT Authorization

Secure JWT-based authorization ensures only authenticated users can access protected routes.
User Management

Admins can create, update, and delete user accounts and assign roles.
Tech Stack


# Frontend:

Handlebars
Bootstrap
TailwindCSS

# Backend:

Node.js
Express.js
MongoDB
bcrypt (for password hashing)
JWT (for authentication)