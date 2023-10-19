# Express Local Library - Simple Book Library CRUD Example

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Starting the Application](#starting-the-application)
- [Usage](#usage)
  - [Create (Adding a Book)](#create-adding-a-book)
  - [Read (Searching for Books)](#read-searching-for-books)
  - [Update (Updating Book Information)](#update-updating-book-information)
  - [Delete (Deleting a Book)](#delete-deleting-a-book)
- [Project Structure](#project-structure)
- [Models](#models)
- [Controllers](#controllers)
- [Views](#views)
- [Routes](#routes)
- [Dependencies](#dependencies)
- [License](#license)
- [Version History](#version-history)
- [Contact Information](#contact-information)
- [Reference](#reference)

## Introduction
### Purpose
The purpose of this project is to provide a simple example of CRUD (Create, Read, Update, Delete) operations using a book library.

## Getting Started
### Installation
Before you can start using the Express Local Library application, make sure you have installed all the prerequisites. Follow these steps:

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/your-repo-url.git
Replace your-repo-url with the actual URL of your project's repository.

Navigate to the project's directory:

bash
Copy code
cd Express_Local_Library
Install the required dependencies using npm:


```javascript
npm install
```
Ensure you have Node.js version 16.15.1 installed. You can check your Node.js version by running the following command:


node -v
If you don't have the correct version of Node.js, you can download it from the official Node.js website.

Additionally, make sure to install Mongoose, a MongoDB object modeling tool, if you haven't installed it already:


```javascript
npm install mongoose
```
Express Local Library uses the Pug templating engine for views. You don't need to install Pug separately, as it comes bundled with Express. However, you should configure your Express application to use Pug as the view engine. Add the following lines to your Express app setup in app.js:

## Populating the Database with Predefined Data
The Express Local Library application includes predefined data that can be loaded into the database using the populatedb.js script. To populate the database, run the following command:


**'node populatedb.js mongodb:host:27107/database**'
Replace mongodb:host:27107/database with the actual connection string for your MongoDB instance. This command will load the predefined data into the database, allowing you to work with sample records.

## Starting the Application
Once you've installed all the prerequisites, you can start the Express Local Library application. You have the option to specify the port as an environment variable or use the default port, which is 3000.

Option 1: Specifying the Port as an Environment Variable

You can specify the port you want the application to run on by setting an environment variable. This allows you to choose a custom port. For example, to run the application on port 8080, you can use the following command:

```javascript
PORT=8080 npm run start
Option 2: Using the Default Port (3000)
```

If you don't specify a custom port, the application will run on the default port, which is 3000. You can start the application without specifying the port as follows:


**npm run start**
Whichever option you choose, the application will start, and you can access it by navigating to http://localhost:3000 or the specified port in your web browser.

Now, you're ready to use the Express Local Library application and explore its features for managing your book library efficiently.

## Usage
The Express Local Library application allows users to perform various operations related to managing books, authors, book instances, and genres. This section provides a brief overview of how to use the application for different tasks.

### Create (Adding a Book)
To add a new book to the library, follow these steps:

Open your web browser and navigate to the Express Local Library application running at http://localhost:3000 or the appropriate URL.

Click on the "Add Book" option, which might be available on the home page or in the navigation menu.

Fill out the required information, including the book's title, author, summary, ISBN, and genre. You can also specify the number of copies available in the library.

Click the "Submit" or "Add Book" button to create a new book record.

### Read (Searching for Books)
To search for books and retrieve book information, use the search functionality:

Visit the Express Local Library application at http://localhost:3000.

Utilize the search bar, which may be available on the home page or a dedicated search page.

Enter keywords, such as a book title or author name, and submit your search query.

View the search results to find books that match your query. Click on a book to access detailed information.

### Update (Updating Book Information)
To update information about a book, follow these steps:

Access the Express Local Library application and find the book you want to update.

Click on the book's title or a "Edit" or "Update" button associated with the book.

Modify the book's details as needed, such as the title, author, summary, ISBN, genre, or available copies.

Save your changes by clicking an "Update" or "Save" button.

### Delete (Deleting a Book)
To remove a book from the library, use the delete operation:

Navigate to the Express Local Library application and find the book you want to delete.

Locate the "Delete" option, which may be available on the book's detail page.

Confirm the deletion by clicking "Delete" or a similar button. The book record will be removed from the library.

The application's user interface is designed to make it easy to interact with the library's data. Users can add, search for, update, and delete books and authors as well as manage book instances and genres seamlessly.

Feel free to explore the different features and functionalities provided by the Express Local Library application to manage and browse your library's collection effectively.

## Project Structure
The Express Local Library project follows a well-organized directory structure that adheres to best practices for maintainability and scalability. Here's an overview of the key directories and their purposes:

### Express_Local_Library: The root directory of the project.

### app.js: The main entry point for the Express application, where application configuration and routes are defined.

### bin: This directory contains the application startup script.

### www: The script responsible for launching the web server and configuring the server to listen on a specified port.

### package.json: The project's package.json file, which contains metadata and dependencies information.

### package-lock.json: The package-lock.json file that records the exact versions of dependencies used in the project.

### public: The directory for storing static assets like stylesheets, images, and JavaScript files.

### stylesheets: A subdirectory under public for storing CSS stylesheets used to style the application's views.

### routes: The directory that contains route definitions and controllers for handling HTTP requests and mapping them to specific actions.

### index.js: The main route file for defining routes related to the application's main functionality.

### users.js: A route file that could be used for user-related functionality if applicable to your project.

### views: The directory containing Pug templates used for rendering dynamic HTML views.

### error.pug: A Pug template for rendering error pages.

### index.pug: The main view template that serves as the home page or landing page of the application.

### layout.pug: A layout template that defines the common structure and components used in various views.

This project structure adheres to a model-view-controller (MVC) architectural pattern, which separates concerns and promotes maintainability and scalability. It's organized in a way that makes it easy to locate and work with different components and files, ensuring a well-structured and readable codebase.

## Models
The Express Local Library project uses Mongoose models to store and manage data related to books, book instances, authors, and genres. Here's an overview of the models:

Book Model: Represents book-related data, including title, copies, author, and more.

Book Instance Model: Controls information about the availability of books and has book status, such as available, maintenance, etc. It depends on the book model.

Author Model: Manages data about authors, including author name, date of birth, and associated books.

Genre Model: Controls data regarding book genres, such as action, science fiction, etc. It depends on books.

The models play a crucial role in defining the data structure and relationships within the application, facilitating CRUD operations and data management.

## Controllers
The controllers in the Express Local Library project perform CRUD (Create, Read, Update, Delete) operations on different categories, including books, authors, book instances, and genres. These controllers handle user requests, interact with the models, and render views for various actions.

## Views
The "views" directory contains Pug templates that provide visual information about specific book, book instance, author, and genre details. These templates render information such as the number of books, author names, available book instances, and genre.

## Routes
The "routes" directory is responsible for defining and handling all routes related to performing CRUD operations. It provides an interface for HTTP GET, POST, UPDATE, and DELETE operations on books, authors, book instances, and genres.
Routes defined for the library
catalog/  The home/index page.
catalog/<objects>/  The list of all books, bookinstances, genres, or authors (e.g. /catalog/books/, /catalog/genres/, etc.)
catalog/<object>/<id>  The detail page for a specific book, bookinstance, genre, or author with the given _id field value (e.g. /catalog/book/584493c1f4887f06c0e67d37).
catalog/<object>/create  The form to create a new book, bookinstance, genre, or author (e.g. /catalog/book/create).
catalog/<object>/<id>/update  The form to update a specific book, bookinstance, genre, or author with the given _id field value (e.g. /catalog/book/584493c1f4887f06c0e67d37/update).
catalog/<object>/<id>/delete � The form to delete a specific book, bookinstance, genre, author with the given _id field value (e.g. /catalog/book/584493c1f4887f06c0e67d37/delete)



## Dependencies
The Express Local Library project relies on the following dependencies:

async: A utility module for handling asynchronous operations.
cookie-parser: Middleware for parsing cookies in Express.
debug: A small debugging utility.
express: The core library for building web applications in Node.js.
express-validator: A set of Express.js middlewares that wraps validator.js validator and sanitizer functions.
http-errors: Create HTTP error objects.
luxon: A library for handling dates and times in JavaScript.
mongoose: A MongoDB object modeling tool.
morgan: HTTP request logger middleware for Node.js.
pug: A high-performance template engine for rendering HTML.
License
This project is licensed under the MIT License. For more details, please refer to the LICENSE file.

## Version History
1.0.0: Initial release
Contact Information
For any questions or inquiries related to the project, please contact Fisayo Fasuyi <fasuyifisayo@gmail.com>.

## Reference
If you're interested in learning more about Express.js and Node.js, the following Mozilla Developer Network (MDN) tutorial is a valuable resource that provides in-depth information and examples: https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs

MDN Express/Node.js Tutorial
This tutorial offers comprehensive guidance on building web applications with Express.js and Node.js, making it an excellent companion to further expand your knowledge in web development.





