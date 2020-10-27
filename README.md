# Reverse Engineering Code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Description of Assignment

Provided with an application's code, I had to describe what each functioning component did, and how it worked.

## Table of Contents

* [Installation](#installation)

* [Tests](#test)

* [Description](#description)

* [License](#license)

* [Questions](#questions)

## Installation

Before running the application, be sure to run:

    npm install

and add this to your MySQL database:

    CREATE DATABASE passport_demo;

## Test

Run this command to test:

    node server.js

# Description

### **General** 
This application uses node.js, express.js, passport.js, and sequalize.js to create an email login page that remembers user accounts through a MySQL database. 

### **Server.js and Models** 

When the file server.js is run, necessary npm packages are required, and the port connection is established. 

Configurations for the application are required, and in the config directory, the passport.js file sets the parameters for accessing the data, using passport.js's 'local strategy' method, which authenticates a user's email and password. Within the same directory, middlewear in the isAuthenticated.js file prohibits access to certain html pages without a user inputting the required paramenters. 

Specific paramaters for the email and password, including the hash or "scrambling" of the password happens in the modules directory, which is required by passport. 

An express function is calls middlewear in the 'public' directory, enabling server.js to use the html, js, and css, frontend files when they are called with routes.

The routes are then called, presenting the user with the '/signup' page if the user isn't currently logged in. Otherwise, users are redirected to the '/members' page. 

Lastly, within server.js, the current database is synced using sequelize. 

### **Sign Up** 

The '/signup' page displays a form with an email and password input, above a "Sign Up" button. When a user attempts to input data outside the parameters set by sequalize in the models directory, the signup.js file in the public directory will run the function 'handleLoginErr,' which will alert the user, and end the POST request before reaching routes.

If successful, the signup.js file will successfully send the input data to the api-routes.js file to be written to the database. This file will then redirect the user to the '/members' page using the html-routes.js file. 

On the '/signup' page below the form, is the text "or login here" with a hyperlink on the "here." When clicked, the html-routes.js routes the user to the '/login' page. 

### **Login** 

On the '/login' page, the same form is presented with the header "Sign Up Form" replaced by "Login Form," and the "Sign Up" button is replaced with a "Login" button. 

The same paramaters are required, but when an email is input that is not attached to an account, the page refreshes and removes the user input. If successful, the login.js file will successfully send the input data to the api-routes.js file to be written to the database. 

This file will then redirect the user to the '/members' page using the html-routes.js file.

### **Members** 

The '/members' page displays the user's email with a welcome message by using a GET request in the members.js file. 


## License

Copyright protected under the open source MIT License.

## Questions

If you have any questions, open an issue.
<br>
<br>
More of my work can be found at [aarondig](https://github.com/aarondig).

<img src="https://avatars3.githubusercontent.com/u/70933425?v=4" width="25%" alt="User Image">
    













