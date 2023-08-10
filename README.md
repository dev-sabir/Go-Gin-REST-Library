# Go HTTP Server with Gin Framework - Documentation

This documentation provides an overview of a simple HTTP server built in Go using the Gin framework. The server manages a basic library of books, exposing endpoints to interact with the library.

## Table of Contents

- [Routes and Endpoints](#routes-and-endpoints)
  - [Get All Books](#get-all-books)
  - [Get Book by ID](#get-book-by-id)
  - [Add a New Book](#add-a-new-book)
  - [Checkout a Book](#checkout-a-book)
  - [Return a Book](#return-a-book)
- [Code Structure](#code-structure)
- [Running the Server](#running-the-server)

---

## Routes and Endpoints

### Get All Books

Retrieves a list of all books in the library.

- **HTTP Method:** GET
- **Endpoint:** `/books`
- **Response:** JSON array containing book details (ID, title, author, quantity).

Example cURL command:

```
curl http://localhost:8080/books
```

### Get Book by ID

Retrieves details about a specific book using its ID.

- **HTTP Method:** GET
- **Endpoint:** /books/:id
- **Response:** JSON object containing book details (ID, title, author, quantity).

Example cURL command:

```
curl http://localhost:8080/books/1
```

### Add a New Book

Adds a new book to the library.

- **HTTP Method:** POST
- **Endpoint:** /books
- **Request Body:** JSON object with book details (title, author, quantity)
  Response: JSON object containing the added book details, including assigned ID.

Example cURL command:

```
curl -X POST -H "Content-Type: application/json" -d '{"title": "New Book", "author": "Author Name", "quantity": 3}' http://localhost:8080/books

```

### Checkout a Book

Checks out a book, reducing its available quantity by 1.

- **HTTP Method:** PATCH
- **Endpoint:** /checkout?id=:id
- **Response:** JSON object containing updated book details.

Example cURL command:

```
curl -X PATCH http://localhost:8080/checkout?id=1

```

### Return a Book

Returns a book, increasing its available quantity by 1.

- **HTTP Method:** PATCH
- **Endpoint:** /return?id=:id
- **Response:** JSON object containing updated book details.

Example cURL command:

```
curl -X PATCH http://localhost:8080/return?id=1

```

## Code Structure

The Go code in this project consists of a main application file (main.go) that defines the HTTP server and its routes. The book struct is used to represent book data.

`Please refer to the provided main.go file for the complete code.`

## Running the Server

To run the HTTP server, follow these steps:

1. **Ensure Go is Installed:** Make sure you have Go installed on your system.

2. **Install Dependencies:** Install the necessary dependencies by running the following command:

   ```
   go get -u github.com/gin-gonic/gin
   ```

3. **Run the Server:** Start the server by running the following command:

   ```
   go run main.go

   ```

4. The server will start on http://localhost:8080.
