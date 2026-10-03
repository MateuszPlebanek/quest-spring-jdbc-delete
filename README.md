# Spring JDBC Delete Challenge

Project completed as part of a Spring Boot and JDBC exercise.

## Objective

The goal of this project is to delete an existing school from a MySQL database using Spring Boot and JDBC.

## Technologies Used

- Java
- Spring Boot
- JDBC
- MySQL
- Thymeleaf
- HTML
- Maven

## Features

- Display all schools
- Delete a school by ID
- Use `PreparedStatement`
- Use `executeUpdate()`
- Redirect to the school list after deletion
- Remove the deleted school from the database

## Routes

Display all schools:

```text
http://localhost:8080/schools
```

## Delete a school

```text
http://localhost:8080/school/delete?id=9
```

## JDBC Delete

DELETE FROM school <br>
WHERE id=?; <br>
The `?` placeholder is filled using a PreparedStatement.

## How it Works

- The user calls `/school/delete` with a school ID.
- The controller calls `repository.deleteById(id)`.
- The repository executes the SQL `DELETE` query.
- `executeUpdate()` verifies that one row was deleted.
- The application redirects to `/schools`.
- The deleted school no longer appears in the list.
