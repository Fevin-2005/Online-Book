**Online Books - Library Management System**

*Overview*

The Online Books project is a library management system developed in Java using Spring Boot for back-end RESTful services, Swagger UI for an interactive interface, and PostgreSQL for data storage. This system allows users and admins to manage books, user profiles, and borrowing transactions efficiently through a REST API-based structure.
GitHub Repository: https://github.com/Fevin-2005/Online-Book.git

*Features*

- User and Admin Management: Enables account creation for users and admins, each with distinct privileges.
- Book Inventory Management: Facilitates borrowing, returning, and inventory updates of books.
- Transaction Management: Handles operations related to borrowing and returning books, including automatic inventory adjustments.
- Data Retrieval: Retrieves user profiles, book lists, and transaction history.
Admins have special permissions, including adding new books and managing inventory directly.

*Project Structure*

The project is structured into four main packages, each organized with key layers to implement the application's functionality:
- Books: Manages book details and inventory.
- Exception: Handles custom error responses for specific application exceptions.
- Order: Manages borrowing and returning transactions.
- User: Manages user and admin profiles.

Each package contains the following layers:
- Controller: Contains API endpoints that interface with the application (e.g., /user endpoints for managing user actions).
- Entity: Maps database tables, defining data structure for users, books, and transactions.
- Repository: Manages CRUD operations (Create, Read, Update, Delete) with PostgreSQL.
- Service: Encapsulates business logic and handles data processing and application rules.

*Technology Stack*

- Java JDK: Programming language used for the application.
- Spring Boot: Framework for REST API and dependency management.
- Swagger UI: Interactive web interface to test and interact with API endpoints.
- PostgreSQL: Database for managing data related to users, books, and transactions.
- IntelliJ IDEA: Primary IDE for code development.
- GitHub: Repository for storing and managing code.

*Spring Boot Dependencies*

The project includes various Spring Boot dependencies, which are specified in the pom.xml file. Key dependencies include:
- Spring Web: Enables the creation of RESTful APIs.
- Spring Data JPA: Integrates PostgreSQL with Spring Data for repository operations.
- Spring Boot DevTools: Provides live reload and convenient development support.
- Lombok: Reduces boilerplate code through annotations (e.g., @Getter, @Setter).

*Lambda Functions and REST API Usage*

The project utilizes Lambda functions within the service layer to streamline data processing. Key REST API annotations used include:
- @RestController: Marks a class as a REST controller.
- @RequestMapping: Maps URLs to specific controller methods.
- @Autowired: Injects dependencies into classes.
- @GetMapping and @PostMapping: Define HTTP GET and POST operations, respectively.
- @RequestParam: Extracts query parameters from requests.
- @ManyToOne: Establishes relational mappings between entities, e.g., book-to-user relationship in borrowing transactions.

*How Swagger UI Integrates with the Code*

The Swagger UI interface dynamically generates and documents API endpoints, allowing users and developers to:
1. Manage User and Admin Accounts: Create, retrieve, update, and delete user profiles, as well as view profile details.
2. View and Manage Book Inventory: Retrieve book listings, add new books, and view inventory counts.
3. Borrow and Return Books: Allows users to borrow books (decreasing the available inventory) and return them (replenishing inventory).

*Software Requirements and Downloads*

To run this project, please ensure the following software is installed:

--> Java JDK (version 11 or higher)
- Used as the core programming language for this application.
- Download Link: https://www.oracle.com/java/technologies/javase-jdk11-downloads.html

--> IntelliJ IDEA
- The primary IDE used to code, run, and debug the application.
- Download Link: https://www.jetbrains.com/idea/download/

--> PostgreSQL
- Database for storing and managing data related to users, books, and orders.
- Download Link: https://www.postgresql.org/download/

--> Swagger UI
- Swagger UI is hosted within the project dependencies. Once the project runs, you can access the interface at http://localhost:8080/swagger-ui.html.

*Usage Instructions*

1. Clone the repository:
git clone https://github.com/Fevin-2005/Online-Book.git
2. Open the project in IntelliJ IDEA.
3. Ensure PostgreSQL is installed and running.
4. Configure the database connection in application.properties.
5. Run the project, and access the Swagger UI at http://localhost:8080/swagger-ui.html.

*Important Endpoints*

1. User and Admin Management
POST /user/register: Register a new user or admin.
GET /user/all: Retrieve all user profiles.

2. Book Inventory
POST /books/add: Add a new book to the library.
GET /books/all: Retrieve all available books.

3. Borrowing and Returning
POST /order/borrow: Borrow a book, which reduces available inventory.
POST /order/return: Return a book, updating inventory count.