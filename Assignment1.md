**1.What is OLTP and OLAP**

OLTP (Online Transaction Processing) and OLAP (Online Analytical Processing) are two types of information systems used in businesses for different purposes:

**OLTP (Online Transaction Processing):**

OLTP systems are designed for transactional data processing. They handle day-to-day operations and transactions of an organization.
These systems are optimized for fast and efficient transaction processing, ensuring that individual transactions are processed accurately and reliably.
OLTP systems typically involve a large number of short online transactions such as inserting, updating, and deleting records in a database.
Examples of OLTP applications include order processing systems, banking systems, airline reservation systems, and retail sales systems.
The main characteristics of OLTP systems include concurrency control, atomicity, consistency, isolation, and durability (ACID properties).

**OLAP (Online Analytical Processing):**

OLAP systems are designed for analyzing and querying large volumes of data to support decision-making processes.
These systems enable users to perform complex queries, data mining, and analysis on historical or aggregated data.
OLAP systems typically involve aggregating, summarizing, and analyzing data from multiple sources to provide insights into business performance and trends.
Examples of OLAP applications include business intelligence tools, data mining applications, and executive information systems.
The main characteristics of OLAP systems include support for complex queries, multidimensional data analysis (e.g., slicing, dicing, drilling), and fast response times for analytical queries.
In summary, OLTP systems focus on efficient transaction processing for day-to-day operations, while OLAP systems focus on analyzing and querying large volumes of data to support decision-making and business intelligence.



**2.Differences Between OLTP and OLAP**

Characteristics:

OLTP systems handle numerous small transactions, while OLAP systems manage large volumes of data with complex queries.

Query types:
OLTP systems execute simple, standardized queries, whereas OLAP systems handle more intricate queries.

Operations:
OLTP systems primarily perform operations such as INSERT, UPDATE, and DELETE, whereas OLAP systems focus on SELECT commands to aggregate data for reporting.

Response time:
OLTP systems deliver responses within milliseconds, while OLAP systems may take seconds, minutes, or even hours depending on data volume.

Design:
OLTP systems are tailored to specific industries like retail or banking, while OLAP systems are designed for specific subjects such as sales or inventory.

Source:
OLTP systems derive data directly from transactions, whereas OLAP systems analyze aggregated data from these transactions.

Purpose:
OLTP systems ensure real-time control of essential business operations, while OLAP systems support decision-making, problem-solving, and uncovering insights.

Data updates:
OLTP systems receive short, quick updates initiated by users, whereas OLAP systems undergo periodic refreshes through scheduled batch jobs.

Space requirements:
OLTP systems typically have small space requirements, especially if historical data is archived, whereas OLAP systems generally require more space due to aggregating large datasets.

Backup and recovery:
OLTP systems necessitate regular backups to ensure business continuity and meet legal requirements, whereas OLAP systems can reload lost data from OLTP databases as needed instead of relying solely on regular backups.

Productivity:
OLTP systems enhance end-user productivity, while OLAP systems boost productivity for business managers, data analysts, and executives.

Data view:
OLTP systems present lists of day-to-day business transactions, whereas OLAP systems provide a multi-dimensional view of enterprise data.

User examples:
OLTP systems cater to customer-facing personnel, clerks, and online shoppers, whereas OLAP systems are used by knowledge workers such as data analysts, business analysts, and executives.

Database design:
OLTP systems employ normalized databases for efficiency, while OLAP systems use denormalized databases optimized for analysis.


**3.Database Normal Forms**

Normalization rules are divided into the following normal forms:

First Normal Form

Second Normal Form

Third Normal Form

BCNF

Fourth Normal Form


First Normal Form (1NF):
Each attribute must contain only a single value from its corresponding value set for a given entity.
Columns cannot contain composite data. For instance, a column cannot contain a list of values.
There should be no repeating groups or arrays of data in any column.
No two rows should be identical; each row should have a unique identifier.
All columns should be relevant to the entity, and there should be no unused or redundant columns.
Null values are permitted, but they should represent missing or unknown data rather than a placeholder for a list of values.
The order of rows and columns should not affect the data.

Second Normal Form (2NF):
All non-key attributes must depend on all parts of the primary key, not just a portion of it.
It addresses redundancy by removing fields that are not fully dependent on the primary key.
If a composite primary key is used, all non-key attributes must depend on the entire composite key, not just part of it.
Tables may need to be split to achieve 2NF, resulting in smaller, more manageable tables.
It helps in maintaining data consistency and integrity by avoiding anomalies.
It facilitates easier data retrieval and manipulation by ensuring data is stored in a structured and normalized manner.
Achieving 2NF often requires the use of foreign keys to establish relationships between tables.

Third Normal Form (3NF):
All non-key attributes must depend only on the primary key, not on other non-key attributes.
It removes transitive dependencies by breaking down tables into smaller ones.
It eliminates redundancy by storing each piece of information in only one place.
3NF tables tend to have smaller row sizes and are more efficient for data retrieval and storage.
It improves data integrity by preventing anomalies caused by non-key attributes depending on other non-key attributes.
Ensures that data modifications are straightforward and do not lead to inconsistencies in the database.
Achieving 3NF often requires careful analysis of functional dependencies and proper table design.

Boyce-Codd Normal Form (BCNF):
It's a stricter form of 3NF.
It addresses anomalies caused by non-trivial functional dependencies on candidate keys.
All determinants must be candidate keys.
Achieving BCNF often involves decomposing tables further to eliminate dependencies on non-candidate keys.
It ensures that every attribute is functionally dependent only on the primary key.
BCNF tables are less susceptible to update anomalies compared to lower normal forms.
It's particularly important for databases where maintaining data integrity is critical, such as in financial systems.

Fourth Normal Form (4NF):
It addresses multi-valued dependencies that are not handled by BCNF.
It eliminates the need for additional tables to represent multi-valued dependencies.
Tables in 4NF do not contain repeating groups or multi-valued attributes.
Achieving 4NF often requires decomposing tables and creating new relationships to represent multi-valued dependencies.
It helps in maintaining database consistency by representing complex relationships more accurately.
It simplifies data retrieval and manipulation by reducing the need for joins and other complex queries.
Tables in 4NF are typically more normalized and efficient compared to those in lower normal forms.


**4.Dimensions vs Fact Table and Types of dimensions**

Fact Table:

Content Focus: Fact tables store quantitative, measurable data or metrics, such as sales revenue, quantity sold, or profit margins.

Granularity: They usually contain data at a fine-grained level, capturing detailed transactional information or event occurrences.

Foreign Key Dependency: Fact tables often include foreign keys referencing primary keys from dimension tables to establish relationships between dimensions and measures.

Aggregation: Aggregations such as sums, averages, or counts are commonly performed on numerical values in fact tables to provide insights and analysis.

Size: Fact tables tend to be larger in terms of the number of records due to their detailed transactional data nature.

Change Frequency: Data in fact tables can change frequently, especially in transactional environments where new transactions occur regularly.

Data Type: Attributes in fact tables are primarily numerical or quantitative in nature, though they may include textual descriptions or identifiers.

Temporal Aspect: Fact tables often include timestamps or date-related fields to record when the transaction or event occurred.

Vertical Structure: Structurally, fact tables are organized vertically, with each row representing a unique transaction or event, and each column representing a different measure.

Usage: Fact tables serve as the core source for analytical queries and reporting, providing insights into business performance and trends.

Dimension Table:

Content Focus: Dimension tables store descriptive attributes or context for the data stored in fact tables, such as product names, customer demographics, or geographic details.

Granularity: They typically contain data at a less granular level compared to fact tables, representing categorical or hierarchical information about entities.

Primary Key: Dimension tables have a primary key that uniquely identifies each record, facilitating data retrieval and maintaining data integrity.

Relationship: Dimension tables establish relationships with fact tables through primary key-foreign key relationships, providing contextual information for analytical queries.

Size: Dimension tables are usually smaller in terms of the number of records compared to fact tables, as they represent categories or attributes rather than detailed transactions.

Change Frequency: Data in dimension tables may change less frequently, especially for static attributes like product categories or customer demographics.

Data Type: Attributes in dimension tables are typically textual or categorical in nature, providing descriptive information about entities or categories.

Temporal Aspect: Dimension tables may include effective date ranges to capture historical changes in attributes over time, enabling time-based analysis.

Horizontal Structure: Structurally, dimension tables are organized horizontally, with each column representing a different attribute, and each row representing a unique entity or category.

Usage: Dimension tables enrich the analysis of fact table data by providing contextual information, facilitating slicing, dicing, and filtering of data for deeper insights and decision-making


Types of Dimensions:

1. Conformed Dimensions
A dimension is considered a conformed dimension and is found in many places. A conformed dimension may be included in a single database, several data marts, or data warehouses with several truth tables.

2. Role-Playing Dimensions
For starters, a fact table can contain international keys for the ship date and the shipping date. But for foreign keys, the same date dimension features are valid, such that all foreign keys have the same dimension table added. The date component here plays several roles in the arrival and delivery date of the ship and hence its name.

3. Shrunken Dimensions
A shrunk dimension is another sub-set. For example, the fact table for orders which contain a foreign product main but a foreign product segment, which is in the product table, but is much less granular, may be included in the target fact table. One way to deal with the heterogeneous grain condition is to create a smaller dimension table with the crop group as its primary key. 
If the product dimension is black-snow, a different product type table is usually available, acting as the shrunk dimension.

4. Degenerate Dimensions
The degenerate dimension is given when the dimension attribute is stored in the fact table and not in a separate dimension table. In principle, these are dimensional keys for which no other attributes exist

5. Rapidly Changing Dimensions
An attribute of dimension that varies often is an attribute that changes rapidly. If you do not have to follow the changes, there would be no problem with the fast-changing attribute, but if you have to follow up the changes, a conventional methodology that changes slowly will create major inflation of the dimension. One solution involves moving the attribute to its own dimension with a different foreign key.

6. Junk Dimensions
A single table with various characteristics and irrelevant functionality to preclude a significant amount of international keys from appearing on the fact table is a garbage factor.

7. Inferred Dimensions
A dimension record may not yet be ready when loading reality documents. One approach is to create a null substitution key for all other functions.

8. Slowly Changing Dimensions
Attributes with a nature that would be prone to time shifts. The maintenance of a clear attribute history of improvements in the data warehouse relies on the market necessity.


**5.Snowflake vs Star Schema**
Star Schema:

Structure:
Star schema consists of one or more fact tables referencing multiple dimension tables.
It follows a simple, denormalized structure where each dimension table directly connects to the fact table.

Complexity:
Star schema is relatively simpler and easier to understand and implement compared to Snowflake schema.
It provides a straightforward and intuitive design, making it ideal for simpler analytical needs.

Data Redundancy:
Star schema often results in some data redundancy because dimensions are denormalized.
Redundancy can lead to faster query performance as data is pre-joined within the schema.

Query Performance:
Star schema typically offers better query performance for simple to moderately complex queries.
Joins between fact and dimension tables are simple, resulting in faster query execution.

Flexibility:
Star schema provides high flexibility and agility in querying and reporting.
It's suitable for OLAP (Online Analytical Processing) applications where fast query response times are essential.

Schema Design:
The schema design in star schema is flat and star-shaped, with a central fact table surrounded by dimension tables.

Snowflake Schema:

Structure:
Snowflake schema is a more normalized version of the star schema, where dimension tables are normalized into multiple related tables.
It includes multiple levels of nested dimension tables, resulting in a more complex schema structure.

Complexity:
Snowflake schema is more complex and requires additional effort for design, implementation, and maintenance.
It offers more flexibility in handling complex relationships and hierarchies within dimensions.

Data Redundancy:
Snowflake schema reduces data redundancy by normalizing dimension tables into multiple related tables.
It saves storage space by avoiding duplication of dimension data but may require more joins during query execution.

Query Performance:
Snowflake schema may have slightly slower query performance compared to star schema, especially for complex queries.
Additional joins between normalized dimension tables can impact query execution time.

Flexibility:
Snowflake schema offers greater flexibility in handling complex data relationships and hierarchies.
It's suitable for scenarios where data integrity and consistency are crucial, such as highly normalized data models.

Schema Design:
The schema design in Snowflake schema resembles a snowflake, with a central fact table surrounded by multiple levels of normalized dimension tables.

