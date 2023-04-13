# Introduction to Database Management Systems (DBMS)
## How to store information?

Ancient “database”

**Tally stick**
- Old Stone Age (~50,000 years ago) until 20th century
- record numbers and quantities
- especially for transactions and trade (→ currency)
- enforces consistency!

**Need methods to**
- store data
- manipulate data
- enforce consistency

**Nowadays**

• need reliable and flexible data storage everywhere
- buying something in a shop (price, items in stock etc...)
- making a booking (hotel, travel, car, etc...)
- borrow book from library (incl. reminders etc...)
- any website with a user login
- organising lectures in a university

**Different approaches**

• pen and paper
- intuitive and easy to use
- good for a few customers
- hard to maintain/search/scale
• rolodex 
- easier to maintain/search/scale
- limited space (overall and per customer)
- no structured queries (How many regular customers live in Durham?)

• text files on computer
- flexible space
- complex queries by implementing custom applications
- different query → different application (fixed queries)
- data is scattered (isolation & duplication)
- structure hard-coded in applications (data dependence)
- incompatible file formats

## The Database Approach

### Two main problems with file-based approach
- implicit definition of data structure(only embedded in applications; not stored separately/independently)
- no unified and central access and control(only as imposed by the applications)

### Database (DB): a shared collection of data
- data is logically related(entities/objects, attributes of entities, relations between entities)
- structure of the DB self-describing (data-about-data) (schema / system catalog / data dictionary / metadata)
- data abstraction (separation of internal and external representation)

## Database Management Systems (DBMS)

- Software system to **define, create, maintain and control** access to a DB

### Components in a DBMS
<img width="300" align="right" src="https://user-images.githubusercontent.com/126205612/231870844-96b76c1a-4fac-4429-91d4-25401bf0dff2.png">

- People (any person interacting with the DBMS in any way)
- Procedures(documented instructions on how to use/run the DBMS)
-  Data (incl. metadata)
-  Software (DBMS, operating system, network software, applications)
-  Hardware (from PC to server network)



## Three-Level Architecture
<img width="300" alt="image" align="right" src="https://user-images.githubusercontent.com/126205612/231871375-8ceeabac-467c-49b2-9134-32f54604c799.png">

- internal–conceptual–external level
- similar to API in software development
- realises data abstraction
  - users can access the same databut have different customized views
  - users can change views without affecting other users
  - internal structure can be changed without affecting users

## Roles in a database environment
- end-users
    - naïve users / sophisticated users
 - application developers
    - make use of the DB for a specific purpose
 - database designers
    - logical / physical
 - administrators
    - data administrators (DA) / database administrators (DBA)

### Advantages
- control over data redundancy, consistency, standards
- improved accessibility and productivity (sharing of data, more information from the same amount of data)
- improved security, maintenance, backup/recovery, scaling
### Disadvantages
- complexity, size, cost
- performance (compared to single-purpose systems)
- single point of failure (due to centralisation)


## Overview: The Relational Data Model
<img width="300" alt="image" align="right" src="https://user-images.githubusercontent.com/126205612/231873603-bd9afb4a-7722-4e72-852b-d33526eac372.png">


- relation: table with columns and rows [file]
  - attribute: named column [field]
  - tuple: row [record]
- relational DB: collection of (normalised) relations
- StudentCourses “relates” students and courses
- formal basis: mathematical relations


## Overview: Entity-Relationship (ER) Modelling
<img width="378" alt="image"  align="right"  src="https://user-images.githubusercontent.com/126205612/231874113-aface7e0-a9d8-4c50-aba6-bcc13b157be8.png">

- model for communication
  - non-technical
  - free of ambiguities
  - Unified Modeling Language (UML) (other notations exist)
- **entities** with attributes
- **relationships** between entities
- **constraints** on entities/attributes/relationships
- not identical to Relational Data Model
- top-down approach to database design


##  Overview: Normalization
<img width="441" alt="image"  align="right"  src="https://user-images.githubusercontent.com/126205612/231874442-2c54a35f-0ab8-4fec-9bfa-8b94d890b54e.png">

- **Purpose**: identify a set of relations with desirable properties for the given use case
   - minimal number of attributes
   - attributes with a close logical relationship
   - minimal redundancy (avoid update anomalies)

- bottom-up technique
- validation in top-down design
-  1st, 2nd, 3rd normal form (and more)

## Overview: Querying with SQL

## Structured Query Language (SQL)
- data definition
  - `CREATE TABLE Staff (staffNo VARCHAR(5), IName VARCHAR(15), salary DECIMAL(7,2));`
- data manipulation (updates)
- `– INSERT INTO Staff VALUES (‘SG16’, ‘Brown’, 8300);`
- data manipulation (queries)
  - `SELECT staffNo, IName, salary`
  - `FROM Staff`
  -  `WHERE salary > 10000`

## Overview: Relational Calculus & Relational Algebra

- mathematical backbone of SQL
- theoretical set language operating on relations
- unary operations 
<img width="231" alt="Unary Operations" src="https://user-images.githubusercontent.com/126205612/231875277-95dfbf8d-854e-4c35-91f9-fa3763850f0f.png">

- binary operations

<img width="494" align = "left" alt="Binary Operations" src="https://user-images.githubusercontent.com/126205612/231875346-4f43310e-18a4-45f8-8ad7-9f84629bd415.png">

