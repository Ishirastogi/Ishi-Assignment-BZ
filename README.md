# Betterzila Assignment
Submitted by Ishi Rastogi

## Task Description:
### 1. Code Review and Identification :
Provide a brief description of all routes in the backend system. 

#### /user Route
This code defines an Express router for handling user authentication and profile management operations.
Below is a detailed description of each route and its functionality.

**Middleware: CheckLogged**

- **Description**: The `CheckLogged` middleware verifies if a user is logged in by checking a JWT token stored in cookies. If the token is valid, the user is authenticated and their data is returned. If the user is not authenticated, the next middleware is called.

**Routes**

- **POST /update_profile**
  - **Description**: Updates the user's profile information in the database. It allows users to update their first name, last name, and profile picture based on their email address.

- **GET /checkLogged**
  - **Description**: Checks if the user is logged in. If the user is logged in, it returns a status indicating that the user is already logged in. If not, it returns a status indicating that the user is not logged in.

- **POST /signup**
  - **Description**: Handles user signup. It supports both manual signup and OAuth-based signup (e.g., Google). For manual signup, it verifies the email and password. For OAuth-based signup, it verifies the token and email.

- **GET /checkPending**
  - **Description**: Checks the status of a pending signup. It verifies if the signup process is still pending based on the user's ID.

- **PUT /signup-finish**
  - **Description**: Completes the signup process. It finalizes the user's registration in the database.

- **GET /login**
  - **Description**: Handles user login. It supports both manual login and OAuth-based login. For manual login, it verifies the email and password. For OAuth-based login, it verifies the token and email.

- **POST /forgot-request**
  - **Description**: Initiates a password reset request. It sends an email with a reset link to the user if the provided email is found in the database.

- **GET /forgot-check**
  - **Description**: Checks the status of a password reset request. It verifies if the reset request is valid based on the user's ID and secret.

- **PUT /forgot-finish**
  - **Description**: Completes the password reset process. It updates the user's password in the database after verifying the reset request.

- **GET /checkUserLogged**
  - **Description**: Checks if a user is logged in and returns a message indicating the login status.

- **DELETE /account**
  - **Description**: Deletes the user's account. It verifies the user's authentication before proceeding with the account deletion.

- **POST /otp**
  - **Description**: Sends an OTP (One-Time Password) to the user's email. This is part of a multi-factor authentication process.

- **POST /send_otp**
  - **Description**: Sends an OTP to the user's email and stores the OTP in the database.

- **POST /verify_otp**
  - **Description**: Verifies the OTP provided by the user. It checks the OTP against the one stored in the database and logs the user in if the OTP is correct.

- **GET /logout**
  - **Description**: Logs the user out by clearing the user token cookie.

#### /chat Route
For handling various operations related to user authentication, file uploads, and interactions with the OpenAI API.

**Middleware: CheckUser**

- **Description**: The `CheckUser` middleware verifies if a user is logged in by checking a JWT token stored in cookies. If the token is valid, the user's ID is added to the request body. If the user is not authenticated, an error response is returned.

**Routes**

- **GET /**
  - **Description**: Responds with a welcome message for the ChatGPT API.

- **GET /upload**
  - **Description**: Retrieves the file name associated with a specific chat for a logged-in user.

- **POST /upload**
  - **Description**: Handles file uploads, stores the file on OpenAI, and saves the file ID and name in MongoDB.

- **POST /**
  - **Description**: Handles a user's chat prompt, sends it to OpenAI, and stores the response in the database.

- **PUT /**
  - **Description**: Handles updates to a chat, sends the updated prompt to OpenAI, and stores the response.

- **GET /saved**
  - **Description**: Retrieves saved chats for a logged-in user based on a chat ID.

- **GET /history**
  - **Description**: Retrieves the chat history for a logged-in user.

- **DELETE /all**
  - **Description**: Deletes all chat history for a logged-in user.

- **POST /getfile**
  - **Description**: Retrieves files associated with a specific chat.

- **POST /deletefile**
  - **Description**: Deletes a specific file associated with a chat.


### 2. User Interface Enhancements:
Integrate Dark Mode: Implement a toggle feature that allows users to switch between light and dark themes.
#### Dark Mode Implementation

**Step 1: Define Global CSS Variables**
- Define CSS variables for both light and dark themes.
- Include variables for background color, text color.

**Step 2: Create ThemeContext**
- Create a ThemeContext to manage the current theme across the application.
- Define a context provider component to supply the theme state and a method to toggle the theme.

**Step 3: Apply Global CSS**
- Import the global CSS file into your main application file.
- Use the ThemeContext provider to wrap your application.
- Set up state management in the provider component to toggle between light and dark themes.
- Update the body class based on the selected theme.

**Step 4: Use ThemeContext in Components**
- Consume the ThemeContext in your components to access the current theme and the toggle function.
- Ensure the Auth component's CSS uses the CSS variables defined in the global CSS file.
- Reference the CSS variables for properties like background color, text color to automatically adapt to the current theme.

**Step 5: Implement Theme Toggle**
- Implement a button or toggle switch in your main application file to change the theme.
- Use the context's toggle function to switch between themes when the button is clicked.


### 3. Video Explaination
#### Link :- 


