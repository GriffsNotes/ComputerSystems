# Lecture 2: Database Design
## Recap: Three-Level ANSI-SPARC Architecture

## Three-Level Architecture
<img width="300" alt="image" align="right" src="https://user-images.githubusercontent.com/126205612/231871375-8ceeabac-467c-49b2-9134-32f54604c799.png">

- internal–conceptual–external level
- similar to API in software development
- realises data abstraction
  - users can access the same databut have different customized views
  - users can change views without affecting other users
  - internal structure can be changed without affecting users

### External Level
<img width="342" alt="image" align="right" src="https://user-images.githubusercontent.com/126205612/231877619-8e292925-c0af-49c4-8c48-e097dd8ff952.png">


- users’ view of the DB
- multiple different views of same data (e.g. date: 2022-01-20, 20/01/2022, 20 Jan ‘22)
- adapted to specific needs
- different entities, attributes, relationships
-  possibly derived/calculated/combined (e.g. age derived from date of birth)

### Conceptual Level
- community view of the DB
- shared by all users
- describes **what** data is stored in the DB
  -  entities, attributes, relationships
  -  constraints
  -  security/integrity information
-   logical structure of entire DB
-   must support external views
-   **no** storage-specific details (the “how”)

### Internal Level
- physical representation of the DB
- describes **how** the data is stored
- achieve optimal
   - runtime performance
   - storage space utilisation
- interface to operating system
- compression and encryption
- not clearly separate from physical organisation

<img width="591" alt="image" src="https://user-images.githubusercontent.com/126205612/231878361-720c8a3e-4b6f-4a43-a41a-ee4df8cea63e.png">

- DBMS handles physical organisation
- We mainly focus on the **conceptual** level.

## Database Schema & Database Instance

### DB schema (intension)
- complete description of the database 
- result of DB design process
- should not change afterwards
- multiple external (sub)schemata (different views)
- one conceptual schema (all entities/attributes/relationships)
- one internal schema (low-level description; storage, indexes, etc)

### DB instance (extension/state)
- concrete data in the database at aparticular point in time
- changes frequently (anytime data is inserted, updated, deleted)
- many different instances (states of a DB) may correspond to the same schema

<img width="604" alt="image" src="https://user-images.githubusercontent.com/126205612/231878951-1ea70968-154b-4810-98f5-f95f9cff31a1.png">

## Data Independence

### Logical data independence
- external schemata (views) remain the same if we change the logical structure (i.e. the schema) on the conceptual level

### Physical data independence
- conceptual schema remains the same ifwe change the internal schema (data structures, algorithms, ...)

<img width="551" alt="image" src="https://user-images.githubusercontent.com/126205612/231879212-6e7ea3b3-3ebe-4178-949c-ccce99709cf5.png">


## Database Design

### Three Phases 
<img width="426" align='right' alt="image" src="https://user-images.githubusercontent.com/126205612/231879716-e4f9b706-ee0c-466d-870e-c7aadc3cd074.png">

1. conceptual
2. logical
3. physical

### Conceptual Design
- construct a first, **high-level model** of the data
  - use **entity-relationship (ER)** modelling
  - identify appropriate **entities, attributes, relationships and constraints**
- based on **user’s requirements** specification
- **independent** of any **physical** considerations
- relevant for **conceptual (but also external)** level
- serves as the **fundamental understanding** of the system

<img width="401" alt="image" src="https://user-images.githubusercontent.com/126205612/231880182-b45aaaa1-9636-499f-9692-15bb23ce1cb3.png">

### Logical Design
- construct the **relational data model** of the data
- use the conceptual design
  - map entities / relationships → tables
- use **normalisation** techniques to eliminate dataredundancies and anomalies

<img width="300" alt="image" src="https://user-images.githubusercontent.com/126205612/231873603-bd9afb4a-7722-4e72-852b-d33526eac372.png">


### Physical Design
- describe the **implementation** of the logical design
- the **how** (as opposed to the **what**)
- define specific
  - **storage** structures
  - **access** methods
  - **security** protection
- consider **concrete usage** / transactions
- optimise for **performance**
