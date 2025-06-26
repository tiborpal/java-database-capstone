## Section 1: Architecture Summary

This Spring Boot application employs a dual-controller strategy, utilizing both MVC and REST controllers to serve various client types. Thymeleaf templates are specifically used for server-rendered web dashboards, namely the Admin and Doctor dashboards, providing traditional HTML views. For all other modules, such as Appointments, PatientDashboard, and PatientRecord, REST APIs are exposed, returning JSON responses suitable for mobile applications or single-page frontend clients.

The backend is structured into distinct layers:

* **Controller Layer**: Acts as the entry point, routing requests to either Thymeleaf or REST controllers based on the request type.

* **Service Layer**: Functions as the core of the business logic, applying rules, coordinating workflows, and ensuring separation from data access concerns. All controllers delegate their logic to this layer.

* **Repository Layer**: Handles data access operations, communicating with two different databases. Spring Data JPA is used for MySQL, managing relational data for entities like patients, doctors, appointments, and admin records. Spring Data MongoDB is used for MongoDB, managing document-based data primarily for prescriptions, leveraging its flexibility for varied data formats.

Data retrieved from the databases undergoes **model binding**, where MySQL data is mapped to JPA entities (`@Entity`), and MongoDB data is mapped to document objects (`@Document`). These bound models are then used by the application for response generation: either rendered into dynamic HTML by Thymeleaf or serialized into JSON for REST API responses. This architecture combines the benefits of server-side rendering with the scalability and flexibility of a RESTful API approach, supported by a robust layered backend and a dual-database persistence strategy.

## Section 2: Numbered Flow – Request/Response Cycle from Frontend to Database

Here's a step-by-step breakdown of the request/response cycle within the application:

1.  **User Interface Interaction**: A user accesses the application through either a Thymeleaf-based web dashboard (e.g., AdminDashboard, DoctorDashboard) or a REST API client (e.g., mobile app, frontend module like Appointments, PatientDashboard, or PatientRecord).

2.  **Controller Routing**: When the user interacts (e.g., clicks a button, submits a form), the request is routed to the appropriate backend controller. Requests for server-rendered views are handled by Thymeleaf Controllers, while requests from API consumers are handled by REST Controllers.

3.  **Service Layer Delegation**: All controllers delegate their processing logic to the central Service Layer. This layer applies business rules, performs validations, and coordinates workflows.

4.  **Repository Layer Communication**: The Service Layer communicates with the Repository Layer to perform necessary data access operations. Depending on the data type, it interacts with either MySQL Repositories (using Spring Data JPA for relational data) or MongoDB Repository (using Spring Data MongoDB for document-based data).

5.  **Database Access**: Each repository interfaces directly with its underlying database engine. MySQL stores core relational entities (e.g., patients, doctors, appointments), while MongoDB stores flexible, nested data structures (e.g., prescriptions).

6.  **Model Binding**: Once data is retrieved from the database, it undergoes model binding. For MySQL, data is converted into JPA entities (`@Entity`). For MongoDB, data is loaded into document objects (`@Document`). These become the consistent Java model classes used across application layers.

7.  **Response Generation**: Finally, the bound models are used to generate the response. In MVC flows, these models are passed to Thymeleaf templates and rendered as dynamic HTML for the browser. In REST flows, the models (or transformed DTOs) are serialized into JSON and sent back to the client as part of an HTTP response, completing the cycle.
