# Authentication System Implementation Plan

## Overview
This document outlines the steps required to implement the authentication system for the Sleeping Queens card game. The authentication system will allow users to register, log in, and manage their sessions securely.

## Steps for Authentication System Implementation

### 1. Initialize Node.js project
- **Action**: Create a new Node.js project.
- **Details**:
  - Run `npm init` to create a package.json file.
  - Fill in project details such as name, version, description, entry point, etc.
  - Install necessary dependencies (e.g., Express, Mongoose, Passport).

### 2. Set up Express server
- **Action**: Configure the Express server.
- **Details**:
  - Create an `app.js` file to set up the server.
  - Use `express()` to create an instance of the app.
  - Set up middleware for parsing JSON and URL-encoded data.
  - Define routes for handling requests.

### 3. Configure MongoDB connection
- **Action**: Establish a connection to MongoDB.
- **Details**:
  - Install Mongoose with `npm install mongoose`.
  - Use Mongoose to connect to the MongoDB database.
  - Handle connection events (e.g., success, error).

### 4. Set up testing environment
- **Action**: Implement a testing framework.
- **Details**:
  - Install Jest or Mocha for testing.
  - Create a `tests` directory for test files.
  - Write initial tests for basic functionality.

### 5. Configure ESLint and Prettier
- **Action**: Set up code linting and formatting.
- **Details**:
  - Install ESLint and Prettier with `npm install eslint prettier`.
  - Create configuration files for ESLint and Prettier.
  - Add scripts to package.json for linting and formatting.

### 6. Create User model
- **Action**: Define a Mongoose schema for the User model.
- **Details**:
  - Create a `models` directory and a `User.js` file.
  - Define fields for username and password with validation rules.
  - Export the User model for use in other parts of the application.

### 7. Add password hashing
- **Action**: Implement password hashing.
- **Details**:
  - Install bcrypt with `npm install bcrypt`.
  - Use bcrypt to hash passwords before saving them to the database.
  - Implement a method to compare hashed passwords during login.

### 8. Install and configure passport-local strategy
- **Action**: Set up Passport for authentication.
- **Details**:
  - Install Passport and the local strategy with `npm install passport passport-local`.
  - Configure Passport to use the local strategy for username/password authentication.
  - Implement serialization and deserialization of user instances.

### 9. Implement serialize/deserialize user functions
- **Action**: Define functions for session management.
- **Details**:
  - Implement `serializeUser` and `deserializeUser` functions.
  - Use these functions to manage user sessions in Express.

### 10. Create login.ejs view
- **Action**: Design the login page.
- **Details**:
  - Create a `views` directory and a `login.ejs` file.
  - Use Bootstrap for styling and layout.
  - Include a form for username and password input.

### 11. Create register.ejs view
- **Action**: Design the registration page.
- **Details**:
  - Create a `register.ejs` file in the views directory.
  - Use Bootstrap for styling and layout.
  - Include a form for new users to create an account.

### 12. Implement /login route
- **Action**: Create a route for login requests.
- **Details**:
  - Define a POST route for `/login`.
  - Use Passport's `authenticate` method to handle login.
  - Redirect users upon successful login or return an error message.

### 13. Implement /register route
- **Action**: Create a route for user registration.
- **Details**:
  - Define a POST route for `/register`.
  - Validate input and create a new user in the database.
  - Redirect users to the login page upon successful registration.

### 14. Implement /logout route
- **Action**: Create a route for user logout.
- **Details**:
  - Define a GET route for `/logout`.
  - Use Passport's `logout` method to terminate the session.
  - Redirect users to the login page.

### 15. Add middleware for protected routes
- **Action**: Implement middleware for route protection.
- **Details**:
  - Create a middleware function to check if a user is authenticated.
  - Apply this middleware to routes that require authentication.

### 16. Configure session store
- **Action**: Set up a session store.
- **Details**:
  - Install a session store (e.g., connect-mongo) with `npm install connect-mongo`.
  - Configure the session store to manage user sessions effectively.

### 17. Add session middleware
- **Action**: Integrate session middleware into the Express application.
- **Details**:
  - Use `express-session` to manage sessions.
  - Configure session options (e.g., secret, resave, saveUninitialized).

### 18. Implement session cleanup
- **Action**: Define a mechanism for session cleanup.
- **Details**:
  - Implement a scheduled task to remove expired sessions from the session store.

### 19. Allow guest players to join
- **Action**: Create a temporary user session for guest players.
- **Details**:
  - Implement logic to allow guest players to join games without registration.
  - Store guest player data in memory.

### 20. Update login.ejs
- **Action**: Include a "Play as Guest" button.
- **Details**:
  - Add a button to the login page for guest access.
  - Implement functionality to handle guest logins.

### 21. Modify the /login route
- **Action**: Handle guest logins.
- **Details**:
  - Update the login route to create a temporary session for guest players.
