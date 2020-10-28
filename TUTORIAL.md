# Reverse Engineering Code Tutorial

In this tutorial we will go into detail on what each file does and how it ineracts with other files an as a whole.

<br />

## Table of Contents

- [Config](#config)

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
