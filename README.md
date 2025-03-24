
# Bookstore RESTful API

A Spring Boot application providing a RESTful API to manage books in a bookstore, built with MySQL, DTOs, and a modular service implementation.

## Project Overview

- **Purpose**: Manage books with CRUD operations.
- **Tech Stack**: 
  - Spring Boot 3.x
  - Spring Data JPA (MySQL)
  - Hibernate (ORM)
  - Validation API
  - Swagger (API documentation)
- **Database**: MySQL (`book_store_db`)
- **Endpoints**: 5 RESTful endpoints for book management.

## Requirements

- **Java**: 17 or higher
- **Maven**: For dependency management and build
- **MySQL**: Local instance running on port 3306
- **Swagger**: Accessible at `http://localhost:8080/swagger-ui.html`

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone (https://github.com/Gathuh/Book-Store-Rest-API)
   cd bookstore-api
 

2. **Configure MySQL**:
   - Create the database:
     ```sql
     CREATE DATABASE book_store_db;
     ```
   - Update `src/main/resources/application.yml` if your MySQL credentials differ:
     ```yaml
     spring:
       datasource:
         url: jdbc:mysql://localhost:3306/book_store_db
         username: 
         password: 
     ```

3. **Build and Run**:
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```
   - App runs on `http://localhost:8080`.

4. **Access Swagger**:
   - Open `http://localhost:8080/swagger-ui.html` to test endpoints.

## Project Structure

- `com.test.project.model`: `Book` entity
- `com.test.project.dto`: `BookDTO` for data transfer
- `com.test.project.repository`: `BookRepository` (JPA)
- `com.test.project.service`: `BookService` (interface), `BookServiceImpl` (implementation)
- `com.test.project.controller`: `BookController` (REST endpoints)
- `com.test.project.exception`: Custom exceptions and global handler

## API Endpoints

| Method | Endpoint            | Description            | URL                                      |
|--------|---------------------|------------------------|------------------------------------------|
| GET    | `/books`           | Retrieve all books     | `http://localhost:8080/books`           |
| GET    | `/books/{id}`      | Retrieve a book by ID  | `http://localhost:8080/books/{id}`      |
| POST   | `/books`           | Create a new book      | `http://localhost:8080/books`           |
| PUT    | `/books/{id}`      | Update a book by ID    | `http://localhost:8080/books/{id}`      |
| DELETE | `/books/{id}`      | Delete a book by ID    | `http://localhost:8080/books/{id}`      |

### Payload Examples

- **POST /books**:
  ```json
  {
    "title": "The Hobbit",
    "author": "J.R.R. Tolkien",
    "price": 14.99,
    "publishedDate": "1937-09-21"
  }
  ```

- **PUT /books/{id}**:
  ```json
  {
    "title": "The Hobbit (Updated)",
    "author": "J.R.R. Tolkien",
    "price": 19.99,
    "publishedDate": "1937-09-21"
  }
  ```

## Validation Rules

- `title`: Must not be empty
- `author`: Must not be empty
- `price`: Must be positive

## Exception Handling

- **404 Not Found**: When a book ID doesn’t exist
- **400 Bad Request**: For validation errors (e.g., empty title, negative price)
- **500 Internal Server Error**: For unexpected issues

## Screenshots


  - **POST /books/{id}**:
  - ![Create Book](https://github.com/Gathuh/Book-Store-Rest-API/blob/main/Screenshot%20from%202025-03-24%2011-02-31.png )
- **GET /books**:  
  [![Get All Books]()](https://github.com/Gathuh/Book-Store-Rest-API/blob/main/Screenshot%20from%202025-03-24%2011-03-47.png)
- **GET /books/{id}**:  
  ![Get Book by ID](https://github.com/Gathuh/Book-Store-Rest-API/blob/main/Screenshot%20from%202025-03-24%2011-04-17.png)
  

  
- **PUT /books/{id}**:

  ![Update Book](https://github.com/Gathuh/Book-Store-Rest-API/blob/main/Screenshot%20from%202025-03-24%2011-05-56.png)
- **DELETE /books/{id}**:  
  ![Delete Book](https://github.com/Gathuh/Book-Store-Rest-API/blob/main/Screenshot%20from%202025-03-24%2011-06-51.png)

## Testing

- Use Swagger UI at `http://localhost:9090/swagger-ui.html`.
- Follow the workflow:
  1. Create a book (`POST`).
  2. List all books (`GET`).
  3. Get a specific book (`GET /{id}`).
  4. Update the book (`PUT`).
  5. Delete the book (`DELETE`).

## Dependencies

Defined in `pom.xml`:
- `spring-boot-starter-web`
- `spring-boot-starter-data-jpa`
- `mysql-connector-java`
- `spring-boot-starter-validation`
- `springdoc-openapi-starter-webmvc-ui`

## Notes

- Ensure MySQL is running before starting the app.
- Update screenshot URLs with your GitHub links.
```
