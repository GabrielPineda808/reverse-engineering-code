# Reverse Engineering Code Tutorial

In this tutorial we will go into detail on what each file does and how it ineracts with other files an as a whole.

<br />

## Table of Contents

- [Config](#config)
- [Models](#models)
- [Public](#public)
- [Routes](#routes)
- [Server](#server)

<br />

---

<br />

## Config

<br />

The Config folder contains files used for connections to the server and user login authentication.

<br />

1. `Middleware` - A folder that contains a file called `isAuthenticated.js` which will not allow the user certain to access certain routes without signing in or up.

<br />

- [middleware](img\middleware.PNG)

The code above is using a function that checks if the user is logged in to let the application know that if the requested object is a user to direct the user to the requested route. If not a user it directs them to the login page.


<br />

2. `config.json` - Provides connection to the mysql server.

<br />

- [config](img\config.PNG)
<br />

Allows the user to connect to its local mysql server by using its own databse, password, and port.

<br />

3. `passport.js` - Authentication with `Passport-local` to log in with an email address and password.

<br />

- [passport](img\passport.PNG)
<br />

Passport.js requires passport and passport-local. Passport-local is a strategy for authenticating via username and password.

Users will login in using an email address which we have assigned for the username field. The application will then in the database if the user's email address and password are valid. If the email address or password are incorrect, the user will be prompted of the incorrect email/password.

To keep the authentication state across HTTP requests. `Passport.serializeUser` and `Passport.deserializeUser` are used.

`Passport.serializeUser` - Determines which data of the user object should be stored in the session which we have deemed as "User".

`Passport.deserializeUser` - Corresponds to the key of the user object that was given to the done function of `Passport.serializeUser`. 

<br />

---

<br />

## Models

<br />

The Models folder contains files needed to connect to the database in order to retrieve and create user data.

<br />

1. `index.js` - Connects to database and imports users data logs.

<br />

- [indexjs](img\indexjs.PNG)
<br />

2. `user.js` - Creates user information that is stored into the database. Uses `bcrypt` for password hashing to create a more secure database.

<br />

- [userjs](img\userjs.PNG)
<br />

`Bcrypt` is required for password hashing. 

First the User model is created based off the user's input of email address and password. If the username and password are valid it redirect if else it will just return with blank form fields.

`Bcrypt` is used to compare if the user provided password matches a hashed password in the database. 

`Bcrypt` is also used to hash a new password before it is created.

<br />

---

<br />

## Public

<br />

The Public folder contains html needed for the front end of the application in order to display it.

<br />

1. `js` - This folder contains validation for the login, members, and signup pages.

    - login.js - Login validation

    - members.js - Checks to see which user is logged in and updates the html page.

    - signup.js - New user creation validation

<br />

2. `stylesheets` - Contains CSS styling for the front end.

    - style.css - styling

<br />

3. `login.html, members.html, signup.html` - Page layouts.

<br />

---

<br />

## Routes

<br />

The Routes folder contains files used to  route the user's data and display the correct data.

<br />

1. `api-routes.js` - Routes for logging in and getting users data to be displayed.

<br />

- [Routes](img\routes.PNG)

<br />

Models and Passport are required. 

`Passport.authenticate("local")` will check if the user is valid in orde to direct them to the members page.

`app.post("/api/signup")` function is used to for signing up a user. 

`app.get("/logout")` function used to log out the user.

`app.get("/api/user_data")` function is used to retrieve user data.

<br />

2. `html-routes.js` - Routes to authenticate the user's login and re-direct the user to the correct html page.

<br />

- [Routes](img\routes.PNG)
<br />

Path is required (it calls the module of the isAuthenticated.js), then isAuthenticated is used to check if the user is logged in.

`app.get("/")` function is used to direct the user to the members page if they have a valid account or the signup if they do not.
`app.get("/login")` function is used to direct the user to the member page or send them to the login page if they do not.

`app.get("/members")` function will check if the user is logged in with their information before accessing the members page if not then theyll be sent to the signup page.

<br />

---

<br />

## Server

<br />

The server.js file requires packages, sets up PORTS, creates express, middleware, routes, and syncs the database. 

<br />

- [Routes](img\server.PNG)
<br />

Requires the necessary NPM packages used to run the application.

Sets up the port and syncs it to the models directory for the database.

Creates an express app to configure middleware needed for the authentication.

`Express-sessions` is used to keep track of login status.

Requires the routes to correspond to the correct file in the `Routes` folder.
