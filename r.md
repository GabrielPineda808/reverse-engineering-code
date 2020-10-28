# Reverse Engineering Code Tutorial

In this tutorial I will be walking you through the functionality of the code used to create a login webapp using Passport.js and other languages. I will be showing how the code communitcates with eachother to create and run the webapp.

---

<br />

## Table of Contents

- [Application Description](#application)
- [Technologies](#technologies)
- [Description](#description)
- [How to install](#installation)

<br />

---

<br />

## Application

<br />

This application generates a website through node.js that has a sign up page and login page. Using passport.js the user is able to create an account using an email and password of their choice then are able to login using the credentials they signed up with. The site will not allow the user to enter it without first creating an accountt or loggin into a previously made account.

<br />

---

<br />

## Technologies

<br />

Technologies used in this project:

- `express` - node.js webapp framework
- `sequelize` - ORM
- `mysql` - mysql client 
- `express-session` - a session middleware
- `passport` - authentication middleware
- `passport-local` - authentication with a username and password
- `bcryptjs` - a way to provide password security

<br />

---

<br />

## Description

<br />
Description of each file.

- `config`

    - middleware
        - isAuthenticated.js - Makes it so the user cannot access certain routes without first loggin in or creating an account.
    
    - config.json - Configuration to connect to mysql database.

    - passport.js - Authentication to log in via email address and password.

- `models`

    - index.js - Connects to database and imports users data logs.

    - user.js -  Uses `bcrypt` for password hashing to create a secure database.WW

- `public`
    - js
        - login.js - Login validation

        - members.js - Checks to see which user is logged in, in order update the html page.

        - signup.js - Creation validation for new users

- `routes`

    - api-routes.js - Routes for logging in and displaying users data.

    - html-routes.js - Authenticate the user login and re-directs the user to the login html page.

- `package.json` - Contains dependencies.

- `server.js` - Requires packages, sets up PORTS, creates express, middleware, routes, and syncs the database.

<br />
---

<br />

## Installation

<br />

1. You must first clone the following github repository into your computer

<br />

```
git clone https://github.com/GabrielPineda808/reverse-engineering-code.git
```

<br />

2. Then inside of the repositories terminal you can install the dependencies.

<br />

```
npm install
```

<br />

3. In mysql workbench, create a new MySQL database and name it `passport_demo`.

<br />

4. In the `config` folder update the `config.json` file's `development` object to match your own local MySQL database(usernam, password, and port).

<br />

5. Start local host server with server.js by using the terminal.

<br />

```
node server.js
```
<br />

6. Open your local host in the browser of choice (example below of url).
```
    http://localhost:8080/
```

<br />

---

<br />