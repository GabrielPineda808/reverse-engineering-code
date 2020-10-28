# Reverse Engineering Code Tutorial

In this tutorial I will be walking you through the functionality of the code used to create a login webapp using Passport.js and other languages. I will be showing how the code communitcates with eachother to create and run the webapp.

---

<br />

## Table of Contents

- [Application Description](#application)
- [Technologies](#technologies)
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