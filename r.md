# Reverse Engineering Code Tutorial

In this tutorial I will be walking you through the functionality of the code used to create a login webapp using Passport.js and other languages. I will be showing how the code communitcates with eachother to create and run the webapp.

---

<br />

## Table of Contents

- [Application Description](#application)
- [Technologies](#technologies)

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
