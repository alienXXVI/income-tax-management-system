# Income Tax Management System (IRRF)

## Description
This project is a database-driven management system designed to handle complex relationships between taxpayers and the Brazilian Internal Revenue Service (RFB) requirements. It allows users to register taxpayers, track their taxable income, manage their assets (properties, vehicles, etc.), and link dependents under specific kinship rules. The application acts as a bridge between a Java interface and a relational MySQL database.

## Technologies
-   **Java SE** (Java 11+)
-   **MySQL** (Relational Database Management System)
-   **JDBC** (Java Database Connectivity)
-   **DAO Pattern** (Data Access Object)

## Features
-   **Comprehensive CRUD Operations**: Create, read, update, and delete records for Taxpayers, Dependents, Companies, and Assets.
-   **Relational Data Management**: Handles complex associations such as addresses (City, State, Neighborhood), taxpayer contacts (Email, Phone), and asset types.
-   **Tax Declaration Tracking**: Specific modules to manage annual IRRF declarations and taxable income sources.
-   **Database Persistence**: Robust connection management via a dedicated Connection class to interface with MySQL.

## How to Run


### Prerequisites

-   **Java Development Kit (JDK)** 11 or higher installed.
-   **MySQL Server** running locally or remotely.
-   **MySQL Connector J** library (included in the `lib/` folder).
    

### Step-by-Step Instructions

1.  **Database Setup**:
    
    -   Create a MySQL database.
    -   Configure the database credentials (URL, user, password) in the `src/conexao/Conexao.java` file.
        
2.  **Compilation**:
    
    -   Ensure the `mysql-connector-j-8.0.33.jar` is included in your classpath.
    -   Compile the source files from the `src/` directory.
        
3.  **Execution**:
    
    -   Run the main application class:
    
    ```
    java -cp "bin;lib/mysql-connector-j-8.0.33.jar" App
    
    ```
    
    _(Note: Use `:` instead of `;` as a separator on Linux/macOS)._

## Project Structure

-   **`src/entity/`**: Contains Plain Old Java Objects (POJOs) representing the system's data models (e.g., `Contribuinte.java`, `Bem.java`).
-   **`src/DAO/`**: Contains the Data Access Object classes responsible for executing SQL queries and managing database persistence for each entity.
-   **`src/conexao/`**: Contains the `Conexao.java` class used to establish and close the JDBC connection to MySQL.
-   **`src/App.java`**: The main entry point of the application.
-   **`lib/`**: Contains the necessary `.jar` dependencies for database connectivity.

## What I Learned

-   **Persistence Patterns**: Implementing the DAO pattern to separate business logic from data access code, improving maintainability.
-   **Relational Mapping**: Manually mapping database tables to Java objects and handling foreign key relationships within a software environment.
-   **JDBC Proficiency**: Managing database drivers, handling SQL exceptions, and utilizing `PreparedStatement` for secure data entry.

## Future Improvements

-   **Graphical User Interface (GUI)**: Transition from a console-based or basic application to a full Swing or JavaFX desktop interface.
-   **Reporting Module**: Generate PDF summaries of taxpayer declarations and asset lists.
-   **Automated Calculations**: Implement logic to automatically calculate tax owed based on current Brazilian tax brackets and deductions.




