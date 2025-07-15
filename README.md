# Church Manager
This repository contains the backend application for the Church Manager system, built with Java Spring Boot. It provides a robust API for managing church-related data, including members, events, collections, and more. This system is designed to be open-source and can be integrated with various frontend and mobile applications.

## Features
The Church Manager Backend provides the following core functionalities
* **Member Management:** Register, update, and manage church members
* **Event Management:** Create, schedule, and track church events
* **Collection Management:** Record and manage church collections/offerings
* **Reporting:** Generate reports based on church data
* **API Endpoints:** Secure and well-documented RESTful APIs for frontend and mobile consumption

## Technologies Used
* **Backend:** Java, Spring Boot
* **Database:** MySQL
* **Build Tool:** Maven

## Getting Started
Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites
Before you begin, ensure you have the following installed:
* **Java Development Kit (JDK):** Version 17 or higher.
* **Apache Maven:** Version 3.x or higher.
* **MySQL Server:** Version 8.x or higher.
* **Git:** For cloning the repository

### Cloning the Repository
You can get the application by cloning the repository from 
```
GitHub:git clone https://github.com/iyf-thika/church_manager_backend_java.git
cd church_manager_backend_java
```

### Database Setup
1. **Create a MySQL Database:**
Open your MySQL client (e.g., MySQL Workbench, command-line client) and create a new database.
```
CREATE DATABASE church_manager;
```

2. **Configure Database Credentials:**
The Spring Boot application uses Hibernate to automatically manage the schema based on your entities. You just need to provide the correct database connection details.

### Application Configuration
Navigate to the ```src/main/resources``` directory and open the ```application.properties``` file (or ```application.yml``` if you prefer YAML).
Update the database connection properties to match your MySQL setup:

```
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/church_manager_db?useSSL=false&serverTimezone=UTC
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA/Hibernate Configuration
spring.jpa.hibernate.ddl-auto=update # Use 'update' for development, 'none' for production
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

# Server Port (Optional, default is 8080)
server.port=9874
```
**Note:** For production environments, it's recommended to use ```spring.jpa.hibernate.ddl-auto=none``` and manage schema migrations using tools like Flyway or Liquibase.

### Installing Dependencies
Once you have cloned the repository and configured the database, navigate to the project's root directory (```church_manager_backend_java```) in your terminal and install the Maven dependencies:
```
mvn clean install
```
This command will download all necessary libraries and compile the project.

### Building the Application
To build a runnable JAR file of the application, use the following Maven command:
```
mvn package
```

This will create a ```church-manager-backend-java-0.0.1-SNAPSHOT.jar``` (or similar name) in the ```target/``` directory.

### Running the Application
You can run the Spring Boot application in a few ways:
1. **Using Maven (for development):**
```
mvn spring-boot:run
```
The application will start on the port configured in ```application.properties (default: 8080)```.

2. **Running the JAR file (for deployment):**
After building the application, you can run the generated JAR file:
```
java -jar target/church-manager-backend-java-0.0.1-SNAPSHOT.jar
```
Once the application starts successfully, you should see logs indicating that Spring Boot 
has initialized and mapped various endpoints.

## Related Projects
This backend is part of a larger ecosystem of open-source Church Manager applications.To get a complete system, you might want to check out the following repositories:
* **Mobile App (Android/Flutter):** [mobile application](https://github.com/iyf-thika/church_manager_mobile)
This repository contains the mobile application that consumes the APIs provided by this backend.
* **Frontend (Web Application):** [front end application](https://github.com/iyf-thika/church_manager_backend)
This repository hosts the web-based frontend application designed to interact with this backend
* **Node.js Backend (Alternative Implementation):** [Node Js Backend](=https://github.com/iyf-thika/church_manager_backend)
An alternative backend implementation of the Church Manager system, built with Node.js.

## Contributing
We welcome contributions to this open-source project! If you'd like to contribute, please follow these steps:
* Fork the repository.
* Create a new branch based on ```development``` (```git checkout -b feature/your-feature-name development```).
* Make your changes and commit them (``git commit -m 'Add new feature'```).
* Push to your new branch (```git push origin feature/your-feature-name```).
* Open a Pull Request targeting the ```development``` branch.

## Pull Request Guidelines:
* All Pull Requests must target the ```development``` branch.
* A Pull Request requires at least one reviewer to approve the changes before merging.
* Tests are highly encouraged for new features and bug fixes to ensure stability and prevent regressions.
* Please ensure your code adheres to good coding practices and includes appropriate tests.

## Branching Strategy
This project follows a specific branching strategy to manage development, testing, and releases:
* ```development```: This is the primary branch for active development. All new features and bug fixes are initially merged here. It represents the most current and often unstable version of the application.
* ```staging```: This branch contains the version of the application currently undergoing testing. Changes from ```development``` are merged into staging for quality assurance before moving to ```main```.
* ```main```: This branch represents the last stable and production-ready version of the application. Only thoroughly tested code from staging is merged into ```main```.
* ```releases```: This branch is used to tag stable releases of the application. Each tag on this branch corresponds to a specific version that has been deployed or is ready for deployment.
The flow of changes generally goes from ```development``` -> ```staging``` -> ```main``` -> ```releases```.

## License
This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).
