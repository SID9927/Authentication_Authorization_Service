# Authentication and Authorization Service

This project is a robust JWT-based Authentication and Authorization Service built with Spring Boot. It provides secure user registration, authentication, and protected endpoint access.

## Features

- User registration with email and password
- User authentication and JWT token generation
- Secure endpoint protection using Spring Security
- JWT token validation for authenticated requests
- MySQL database integration for user storage

## Technologies Used

- Java 11
- Spring Boot 2.7.x
- Spring Security
- JSON Web Tokens (JWT)
- MySQL
- JPA / Hibernate
- Maven

## Project Structure

- `src/main/java/com/example/authservice/`
  - `Application.java`: Main Spring Boot application class
  - `Controller/`: Contains REST controllers
  - `Service/`: Service layer for business logic
  - `Repository/`: Data access layer
  - `Entity/`: JPA entities
  - `Model/`: Data transfer objects
  - `Config/`: Configuration classes
  - `Filter/`: Custom filters
  - `Util/`: Utility classes

## Setup and Installation

1. Clone the repository:
   
git clone https://github.com/SID9927/Authentication_Authorization_Service.git


2. Navigate to the project directory:

cd auth-service


3. Configure MySQL database:
- Create a MySQL database named `auth_service`
- Update `src/main/resources/application.properties` with your MySQL credentials

4. Build the project:

mvn clean install

5. Run the application:

mvn spring-boot:run

The service will start running on `http://localhost:8080`.

## API Endpoints

- POST `/register`: Register a new user
- POST `/authenticate`: Authenticate a user and receive a JWT
- GET `/home`: A protected endpoint that requires authentication

## Usage

1. Register a new user:

POST /register { "username": "user@example.com", "email": "user@example.com", "password": "password123" }

2. Authenticate and receive a JWT:

POST /authenticate { "username": "user@example.com", "password": "password123" }

3. Access protected endpoint:

GET /home Header: Authorization: Bearer <your_jwt_token>

## Security Considerations

- Passwords are encrypted using BCrypt before storing in the database
- JWTs are signed with a secret key and have an expiration time
- Protected endpoints require a valid JWT for access

## Future Improvements

- Implement refresh token functionality
- Add role-based access control
- Integrate with OAuth2 for third-party authentication
- Implement email verification for new user registrations

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License.
