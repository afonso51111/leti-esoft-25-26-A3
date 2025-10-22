# OO Analysis

The construction process of the domain model is based on the client specifications, especially the nouns (for _concepts_) and verbs (for _relations_) used.

## Rationale to identify domain conceptual classes
To identify domain conceptual classes, start by making a list of candidate conceptual classes inspired by the list of categories suggested in the book "Applying UML and Patterns: An Introduction to Object-Oriented Analysis and Design and Iterative Development".

### _Conceptual Class Category List_

**Business Transactions**

* `Agendamento` (Appointment): Represents the act of an SNS user scheduling a vaccination.
* `EventoVacinacao` (Vaccination Event): Records the act of administering a vaccine to a user.

---

**Transaction Line Items**

* (At this stage, it can be modeled directly in the transaction, e.g., `EventoVacinacao` records the specific `Vacina` used).

---

**Product/Service related to a Transaction or Transaction Line Item**

* `Vacina` (Vaccine): The specific product (brand, commercial name) administered.
* `TipoVacina` (Vaccine Type): The generic service/product being scheduled and administered (e.g., Covid-19, Influenza).

---

**Transaction Records**

* `CertificadoVacinacao` (Vaccination Certificate): A record issued that proves vaccination.

---

**Roles of People or Organizations**

* `UtenteSNS` (SNS User): The citizen who receives the vaccine.
* `Rececionista` (Receptionist): Staff who manage user arrivals and in-person appointments.
* `Enfermeiro` (Nurse): Staff who administer the vaccine and record the event.
* `AdministradorDGS` (DGS Administrator): Staff who configure the system.

---

**Places**

* `CentroVacunacao` (Vaccination Center): The generic place where vaccination occurs.
* `CentroSaude` (Healthcare Center): A specific type of center.
* `CentroVacinacaoMassiva` (Community Mass Vaccination Center): A specific and temporary type of center.

---

**Noteworthy Events**

* `Chegada` (Arrival): The event of a user arriving at the center.
* `ReacaoAdversa` (Adverse Reaction): An event that may occur after vaccination and must be recorded.

---

**Physical Objects**

* (`Vacina` could be seen as a physical object, but is better classified as 'Product' or 'Description' in this context).

---

**Descriptions of Things**

* `Vacina` (Vaccine): Describes a specific product with a commercial name, brand, and technology.
* `TipoVacina` (Vaccine Type): Describes a vaccine category with a code, disease, and description.
* `TecnologiaVacina` (Vaccine Technology): Describes the technology used in a vaccine.

---

**Catalogs**

* (The system manages catalogs of `CentroVacunacao` and `TipoVacina`, but the concepts themselves are more central than the catalog).

---

**Containers**

* `CentroVacunacao` (Vaccination Center): Contains rooms (e.g., waiting room, recovery room) and staff.

---

**Elements of Containers**

* (N/A for the main domain model).

---

**(Other) Organizations**

* `DGS`: The organization that manages the entire system.

---

**Other (External/Collaborating) Systems**

* (N/A for the domain model, although mentioned in the architecture).

---

**Records of finance, work, contracts, legal matters**

* `HistoricoVacinacao` (Vaccination History): Mentioned as being reviewed by the nurse.

---

**Financial Instruments**

* (N/A)

---

**Documents mentioned/used to perform some work**

* `CertificadoVacinacao` (Vaccination Certificate).

---

## Rationale to identify associations between conceptual classes

An association is a relationship between instances of objects that indicates a relevant connection and that is worth of remembering, or it is derivable from the List of Common Associations:

* **_A_** is physically or logically part of **_B_**
* **_A_** is physically or logically contained in/on **_B_**
* **_A_** is a description for **_B_**
* **_A_** is known/logged/recorded/reported/captured in **_B_**
* **_A_** uses or manages or owns **_B_**
* **_A_** is related with a transaction (item) of **_B_**
* etc.

| Concept (A) | Association | Concept (B) |
| :--- | :---: | ---: |
| `UtenteSNS` | schedules | [cite_start]`Agendamento` [cite: 64] |
| `Rececionista` | registers | [cite_start]`Chegada` [cite: 73] |
| `Rececionista` | schedules (in-person) | [cite_start]`Agendamento` [cite: 69] |
| `Enfermeiro` | registers | [cite_start]`EventoVacinacao` [cite: 79] |
| `Enfermeiro` | registers | [cite_start]`ReacaoAdversa` [cite: 82] |
| `Enfermeiro` | accesses | [cite_start]`HistoricoVacinacao` [cite: 77] |
| `Enfermeiro` | issues | [cite_start]`CertificadoVacinacao` [cite: 56] |
| `AdministradorDGS` | registers / manages | [cite_start]`CentroVacunacao` [cite: 83] |
| `AdministradorDGS` | registers / manages | [cite_start]`Pessoal` (Enfermeiro, Rececionista) [cite: 83] |
| `AdministradorDGS` | configures | [cite_start]`TipoVacina` / `Vacina` [cite: 84, 86] |
| `Agendamento` | occurs at | [cite_start]`CentroVacunacao` [cite: 65] |
| `Agendamento` | is for | [cite_start]`TipoVacina` [cite: 65] |
| `EventoVacinacao` | uses | [cite_start]`Vacina` [cite: 79] |
| `EventoVacinacao` | can cause | [cite_start]`ReacaoAdversa` [cite: 81-82] |
| `Agendamento` | results in | `EventoVacinacao` |
| `Vacina` | is of | [cite_start]`TipoVacina` [cite: 86] |
| `CentroSaude` | is a (type of) | [cite_start]`CentroVacunacao` [cite: 53] |
| `CentroVacinacaoMassiva` | is a (type of) | [cite_start]`CentroVacunacao` [cite: 54] |
| `CentroSaude` | administers (various) | [cite_start]`TipoVacina` [cite: 53] |
| `CentroVacinacaoMassiva` | administers (one) | [cite_start]`TipoVacina` [cite: 54] |

## Domain Model

**Do NOT forget to identify concept atributes too.**

**Place the Domain Model diagram below, using SVG format.**

![Domain Model](svg/DM.svg)

