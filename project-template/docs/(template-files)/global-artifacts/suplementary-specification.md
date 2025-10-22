# Supplementary Specification (FURPS+)

## Functionality

_Specifies functionalities that:  
&nbsp; &nbsp; (i) are common across several US/UC;  
&nbsp; &nbsp; (ii) are not related to US/UC, namely: Audit, Reporting and Security._

* **Authentication:** All system users must be authenticated beforehand.
* **Authentication Simulation:** For the current prototype, the authentication process may be simulated/mocked.
* **Future Flexibility:** The application should be designed to easily accommodate future pandemic scenarios requiring large-scale population vaccination.
* **Commercialization:** The software application should be conceived with potential commercialization in mind, allowing it to be offered to other companies, organizations, or healthcare systems beyond DGS.
* **Security (Data Access):** Only nurses are authorized to access full health data of users.

## Usability 

_Evaluates the user interface. It has several subcategories,
among them: error prevention; interface aesthetics and design; help and
documentation; consistency and standards._

* **Target UIs:** The system envisions multiple dedicated User Interfaces (UI), including a Web Application targeted at DGS staff and a mobile application targeted at SNS users.
* **Prototype UI:** At this stage, the focus is not on developing these UIs. For demonstration purposes, a basic console-based Ul is considered sufficient.
* **Language:** All project artifacts, including source code, must be developed in English.

## Reliability

_Refers to the integrity, compliance and interoperability of the software. The requirements to be considered are: frequency and severity of failure, possibility of recovery, possibility of prediction, accuracy, average time between failures._

* **Availability:** Overall system availability must exceed 99% annually.
* **Failure Recovery:** In the event of failure, no data loss should occur.

## Performance

_Evaluates the performance requirements of the software, namely: response time, start-up time, recovery time, memory consumption, CPU usage, load capacity and application availability._

* **Start-up Time:** The system must start up in less than 10 seconds.
* **Load:** At peak times, the system is expected to experience high loads.
* **Response Time:** It must be designed to ensure a maximum response time of 5 seconds, regardless of load conditions.

## Supportability

_The supportability requirements gathers several characteristics, such as:
testability, adaptability, maintainability, compatibility,
configurability, installability, scalability and more._

* **Multi-Platform Persistence:** The system should be designed to support data persistence across multiple target platforms, including relational databases, NoSQL databases, and in-memory databases.
* **Testability:** The adoption of automated regression testing, preferably using the Google Testing Framework, is strongly recommended and highly valued.
* **Adaptability:** The application should be designed to easily accommodate future pandemic scenarios and be conceived with potential commercialization in mind.

## +

### Design Constraints

_Specifies or constraints the system design process. Examples may include: programming languages, software process, mandatory standards/patterns, use of development tools, class library, etc._

* **Architecture:** The system must comprise (at minimum) the applications and/or components illustrated in Figure 1 , separating a core server-side application (responsible for business logic and data persistence) from client-side applications.
* **API Exposure:** The server-side application exposes multiple APIs to support the development of user applications.
* **Artifact Format:** For readability purposes, all images (such as diagrams) stored in the repository must be in SVG format.

### Implementation Constraints

_Specifies or constraints the code or construction of a system such
such as: mandatory standards/patterns, implementation languages,
database integrity, resource limits, operating system._

* **Language (Core):** The core server-side application is required to be developed in C++.
* **IDE:** The CLion IDE is to be used, preferably.
* **Language (Artifacts):** All project artifacts, including source code, must be developed in English.
* **Version Control System (VCS):** Teams must use GitHub as their version control system throughout prototype development.
* **VCS Storage:** All project artifacts must be stored in the version control repository, including (but not limited to) diagrams, documents, source code, configuration files, and images.
* **Repository Naming Convention:** The GitHub repository name must follow the format `leti-esoft-25-26-[LabClass][TeamNumber]`.

### Interface Constraints

_Specifies or constraints the features inherent to the interaction of the
system being developed with other external systems._

* **Exposed APIs:** The server-side application must expose multiple APIs (PVMS REST API, PVMS Mobile API, PVMS Library API) to support the development of various user applications.
* **API Consumers:** These APIs are consumed by client-side applications, such as the PVMS Web APP, iOS/Android APPs, and the Console APP.
* **API Validation:** Generic HTTP client tools (e.g., Postman) may be used to verify and validate the exposed APIs.

### Physical Constraints

_Specifies a limitation or physical requirement regarding the hardware used to house the system, as for example: material, shape, size or weight._

(fill in here)