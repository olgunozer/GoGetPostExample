# Go Get/Post Example
This is a simple example of a REST API implemented in Go, using the built-in net/http package. The API allows clients to perform basic CRUD operations on a list of users.

## Usage

 1- Clone the repository and navigate to the project directory.
 
 2- Run ```bash go run main.go ``` to start the server.
 
 3- The server will be running on ```bash http://localhost:8080 ```

## Endpoints

The following endpoints are available:

### GET /users

Retrieves a JSON array of all users.

Example response:

```bash
[
    {
        "id": 1,
        "name": "John Doe"
    },
    {
        "id": 2,
        "name": "Jane Doe"
    }
]
```
### POST /users

Creates a new user. Expects a JSON object with an id and a name property.

Example request:

```bash
{
    "id": 3,
    "name": "Bob Smith"
}
```

## Code structure

The code is structured in the following way:

* The **_main_** function sets up the routes and starts the server.
* The **_handleUsers_** function is a router that handles requests to the /users endpoint and delegates to the appropriate handler function.
* The **_handleUsersGet_** function retrieves a list of all users and returns it to the client in a JSON encoded response.
* The **_handleUsersPost_** function reads a user object from the request body, adds it to the list of users, and returns a 201 status code.

Note that the list of users is stored in memory and will be lost when the server is restarted. In a real-world application, this data would be persisted in a database.

## Limitations

- This example does not handle errors, such as invalid JSON in the request body or a non-existent user ID.
- The code does not include any validation for the request, for example, checking if request body is empty.
- The **_handleUsersPost_** function does not check for duplicate user ID
- The example does not include any security feature such as authentication or authorization.
- This is a very simple example, it is not suitable for production use without some modifications.

## Conclusion

This example provides a basic introduction to building a REST API in Go using the **net/http** package. It can be used as a starting point for building a more fully-featured application.



