# Cinema-App

This is a web application designed for educational and demonstration purposes that simulates a ticket reservation system in a cinema. - This is a web application designed for educational and demonstration purposes that simulates a cinema ticket reservation system.
The database already has an injection - The database already contains users:

* Admin: admin@i.ua : admin123
* User: alice@i.ua : alice123
  
### The following principles were followed during the development of the program:

* REST API
* SOLID principles

### Project based on 3-layer architecture:
* Presentation layer (controllers)
* Application layer (services)
* Data access layer (DAO)

## Functionalities
* Register a new user
* Login (with username and password)
* Role-based authorization (admin, user)
* Exception handling (invalid username, password, invalid role) with descriptive messages

## Project has multiple endpoints with user and admin access

*   `POST: /register` (to create a user) - `ALL`
*   `POST: /cinema-halls` (to create a cinema hall) - `ADMIN`
*   `POST: /movies` (to create a movie) - `ADMIN`
*   `POST: /movie-sessions` (to create a movie sessions) - `ADMIN`
*   `POST: /orders/complete` (to create an order for current user) - `USER`
*   `PUT: /movie-sessions/{id}` (to update a movie session) - `ADMIN`
*   `PUT: /shopping-carts/movie-sessions` (to add movie session to shopping cart) - `USER`
*   `DELETE: /movie-sessions/{id}` (to delete a movie session) - `ADMIN`
*   `GET: /orders` (to get order history for current user) - `USER`
*   `GET: /shopping-carts/by-user` (to get a shopping cart for current user) - `USER`
*   `GET: /cinema-halls` (to get all cinema halls) - `USER` or `ADMIN`
*   `GET: /movies` (to get all movies) - `USER` or `ADMIN`
*   `GET: /movie-sessions/available` (to get all available movie by date) - `USER` or `ADMIN`
*   `GET: /users/by-email` (to find user by email) - `ADMIN`

All endpoints send and receive JSON data, except for the login page, which is generated by Spring Security.
Almost all endpoints are secured by role-based authorization. More details can be found in the `SecurityConfig` class.
###  Also, you can use my Postman request collection: [LINK](https://www.postman.com/maintenance-geologist-24055309/workspace/cinema/collection/26843599-49db9a59-ad94-44ef-af7e-25f1becfa9f0?action=share&creator=26843599)
### Video tutorial how to work with Postman and the collection of requests that I created. [LINK](https://www.youtube.com/watch?v=YzvAfXV4GFk)




### Package Structure

* `config` - stores Spring configuration
* `controller` - contains controllers for endpoints
* `dao` - data access layer (repository) that calls CRUD methods in the database
* `dto` - wrapper for model objects to unify the requests and responses in controllers
* `lib` - contains email and password validators with its annotations
* `model` - contains models for the database
* `service` - contains services that call repositories and the Authentication class
* `mapper` - converts model objects to DTO objects

## Technologies

* Java `17`
* Apache Maven `3.10.1`
* Apache Tomcat  `9.0.73`
* MySQL Connector `8.0.22`
* Hibernate `5.6.14.Final`
* Spring: 
    * Core `5.3.20`
    * Web Mvc `5.3.20`
    * Security `5.6.10`

## How to Run and Test

* Clone the repo on GitHub
* Create an empty database
* To set up the database connection parameters, edit the `resources/db.properties` file. 
* Build the project using Maven: `mvn clean install`
* Deploy the generated WAR file to servlet container such as Tomcat

#### You can login as a mock admin or user at localhost:8080/login to test the application's functionalities:
* Admin: admin@i.ua : admin123
* User: alice@i.ua : alice123 

## Contacts

If you have any questions or suggestions, please feel free to contact me via [My LinkedIn](https://www.linkedin.com/in/sergiy-golubchenko-74646485/) 
I am open to new opportunities as a Junior Java Developer.