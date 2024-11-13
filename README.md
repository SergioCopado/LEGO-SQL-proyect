# LEGO Database Migration Project
Course: Databases I, Bachelor’s in Data Science and Artificial Intelligence, ETSI, Universidad Politécnica de Madrid
Contributors: Students of Databases I, supervised by ETSI-SI faculty

## Project Overview
LEGO is modernizing its data storage infrastructure by migrating from a legacy file-based system to a Relational Database Management System (RDBMS). This migration aims to improve the efficiency of inventory management and production control for LEGO sets.

Additionally, LEGO wants to incorporate new functionality to support the "LEGO Ideas" initiative, allowing fans worldwide to submit set proposals. This feature will help LEGO engage with its community and leverage fan creativity to develop potential new commercial products.

## Objectives
The goals of this migration project are:

1. **Data Migration:** To convert existing data from CSV files into a relational database schema that maintains data integrity, enables scalability, and provides robust query capabilities.
2. **Support for LEGO Ideas:** To add functionalities allowing:
    * User registration and unique identification by alias.
    * Proposal submissions of new sets by users, with specifications of required pieces for each set.
    * Tracking of commercial sets that originated from LEGO Ideas proposals, including potential modifications to the pieces in final commercial versions.
3. **Efficiency in Set Production:** To optimize data storage and retrieval to streamline the processes of stocking, piece management, and cost-effective production of commercial LEGO sets.

## Database Requirements and Structure
The database has been designed to incorporate the following main entities and relationships:

### Core Entities
1. **Users:** Registered users identified by a unique alias, who can submit set proposals as part of the LEGO Ideas initiative.
2. **Sets:** Each set can either be a Commercial Set or a LEGO Ideas Proposal, and each may require a specified number of parts for assembly.
3. **Parts:** Individual LEGO pieces, each with a unique identifier, which are used to assemble sets.
4. **LEGO Ideas:** Proposed sets submitted by users. Each set proposal specifies the parts needed, which may be adjusted if the set becomes a commercial product.

### Key Relationships
* **User-Set:** A one-to-many relationship where each user can propose multiple LEGO sets.
* **Set-Part:** A many-to-many relationship, as each set requires multiple parts, and parts can be used in multiple sets.
* **LEGO Ideas to Commercial Set:** A relationship indicating whether a commercial set originated from a user proposal, with potential adjustments in parts to optimize production costs.

## Database Functionalities
The database schema and SQL functionality support the following key operations:

1. **User Registration and Authentication:**
    * Register new users, ensuring each alias is unique.
    * Store and retrieve user profile information.

2. **LEGO Ideas Set Proposals:**
    * Enable users to submit new set ideas with detailed part lists.
    * Maintain records of all set proposals with unique identifiers and track their popularity.
    
3. **Commercial Set Conversion:**
    * Track commercial sets and indicate if a set originated from LEGO Ideas.
    * Adjust part lists for commercial sets as needed based on LEGO’s production requirements.
    
4. **Inventory and Production Management:**
    * Efficiently manage stock levels of each part required for commercial sets.
    * Query part usage across sets to optimize part stock levels and reduce production costs.

## Technical Details
The database was developed using SQL with the following key features:

* **Data Integrity:** Ensures referential integrity with foreign key constraints and unique indices, particularly for unique user aliases and set identifiers.
* **Normalization:** Follows normalization principles to reduce redundancy and improve data consistency across the schema.
* **Query Optimization:** Designed with indexing strategies to support efficient querying of popular data points, such as set popularity and part usage.

## Steps for Migration and Implementation
1. **Data Import:** Convert provided CSV data into SQL tables, using appropriate data types for each field (e.g., integer, varchar, foreign keys).
2. **Schema Design:** Define tables, primary keys, and relationships, following the provided functional requirements.
3. **Data Normalization:** Ensure third normal form (3NF) to minimize redundancy.
4. **LEGO Ideas Functionality:** Implement tables and queries to support user proposals, set conversion, and part adjustments.
5. **Testing and Validation:** Validate data integrity through constraint testing and run sample queries to ensure functionality meets LEGO's requirements.

## License
This project is academic and for demonstration purposes only, with no commercial use permitted.
