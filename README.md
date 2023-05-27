# E-Commerce Application

Fully-featured E-Commerce application from scratch - including production-grade authentication!

## Introduction

<!-- Provide a brief overview of your E-Commerce application, its purpose, and its key features. -->

## Installation

**Prerequisites:**

Ensure that you have Node.js and npm (Node Package Manager) installed on your machine.

**Installation Steps:**

1. Clone the repository or download the source code for your E-Commerce application.

2. Open a terminal or command prompt and navigate to the project's root directory.

3. Run the following command to install the project dependencies listed in the package.json file:

   `npm install`

4. Once the dependencies are installed, create a new file named .env in the project's root directory. This file will store your environment variables. Add the necessary environment variables for your application, such as database connection details or API keys. Refer to your application's specific requirements and documentation for the required environment variables.

5. Start the application by running the following command:

   `npm run dev`

This command will start the application using nodemon, which automatically restarts the server whenever changes are detected.

6. If everything is set up correctly, you should see a message in the console indicating that the server is running. It might be something like:

   `Server started on http://localhost:3000`

This means the application is now running locally on your machine.

7. Open a web browser and visit http://localhost:3000 (or the appropriate URL if specified differently) to access the E-Commerce application.

8. You can now interact with the application, create accounts, browse products, and perform any other functionalities.

Congratulations! You have successfully set up and are now running the E-Commerce application locally. Feel free to explore and test its features.

## Usage

<!-- Explain how users can interact with your application and navigate through its features. Provide examples or screenshots if necessary. -->

## Authentication

<!-- Describe the authentication mechanism used in your application, including instructions on how users can create accounts, log in, and manage their authentication credentials. -->

The `auth.js` file in the project handles the authentication routes and logic. Let's break down how the authentication works:

1. The code requires necessary modules and dependencies at the beginning, including Express, middlewares, the user repository, and templates for signup and signin pages.

2. The `router` object is created using `express.Router()` to define the authentication routes.

3. The `/signup` route handles GET and POST requests for user signup. When a GET request is received, it renders the signup template and sends it as a response. When a POST request is received, it performs input validation using middleware functions (`requireEmail`, `requirePassword`, `requirePasswordConfirmation`). If there are any validation errors, the `handleErrors` middleware is executed, which renders the signup template with the error messages. If there are no errors, it creates a new user in the user repository, sets the `userID` property in the session to the newly created user's ID, and redirects the user to the admin products page.

4. The `/signout` route handles GET requests for user signout. It clears the session by setting it to `null` and sends a response indicating that the user is logged out.

5. The `/signin` route handles GET and POST requests for user signin. When a GET request is received, it renders the signin template and sends it as a response. When a POST request is received, it performs input validation using middleware functions (`requireEmailExists`, `requireValidPasswordForUser`). If there are any validation errors, the `handleErrors` middleware is executed, which renders the signin template with the error messages. If there are no errors, it checks if a user with the provided email exists in the user repository. If a user is found, it sets the `userId` property in the session to the user's ID and redirects the user to the admin products page.

6. Finally, the `router` object is exported to make it available for other parts of the application to use.

In summary, the `auth.js` file handles the routes and logic related to user authentication. It provides routes for user signup, signout, and signin. It performs input validation, creates new users, checks existing users, and manages user sessions using the `req.session` object. The user's ID is stored in the session to keep track of authenticated users.

## Dependencies

**cookie-session:** A middleware that provides session support in Express.js by storing session data in cookies. It encrypts and signs the session data to enhance security.

**express:** A fast and minimalist web application framework for Node.js. It simplifies the development of web applications and APIs by providing a robust set of features and utilities.

**express-validator:** A set of express.js middleware functions for input validation and sanitization. It helps validate and sanitize user input data to prevent security vulnerabilities and ensure data integrity.

**multer:** A middleware for handling multipart/form-data, which is commonly used for file uploads. It simplifies handling file uploads in Express.js applications.

**nodemon:** A tool that helps in development by monitoring changes in your Node.js application files and automatically restarting the server. It eliminates the need to manually restart the server after each code change.

These dependencies are essential for various aspects of the E-Commerce application, including session management, routing, input validation, file handling, and development workflow.

## FAQs / Troubleshooting

<!-- Address common questions or issues that users might encounter and provide solutions or guidance.-->

## Testing

<!-- Explain how to run the tests for your application to ensure its reliability and stability.-->

## Contributing

<!-- If you want to encourage contributions, provide guidelines for contributing to your project. Explain how users can submit bug reports, feature requests, or pull requests.-->
