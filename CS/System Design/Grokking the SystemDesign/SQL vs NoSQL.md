# SQL vs. NoSQL

## SQL

Relational Databases store data in rows and columns. Each row contains all the info about one entity and each column contains all the seperate data points.

MySQL, Oracle, MS SQL, SQLite, Postgres, and MariaDB

## NoSQL

**Key-Value Stores**: Data is stored in an array of key-value pairs. Key is an attribute name which is linked to a value.

ex) Redis, Voldemort and Dynamo

**Document Databases**: Data is stored in documents. Basically like a Json blob

**Wide-Column Databases**: It's not quite a table. But the rows are made of flexible columns

**Graph Databases**: Best represnatation of this database would be nodes of graph

## High level differences

**Storage**

SQL stores data entity that is represented with a row and a column. NoSQL databases have different data storage models. (key, document, columnar and graph)

**Schema**

In SQL, Schemas are fixed but in NoSQL they're dynamic.

**Querying**

Sql uses SQL and NoSQL it's inconsistent. Depends on the database

**Scalability**

Because of Sharing, if a data is spread between servers, when we use SQL database it will have to perform join across the server. Which makes horizontal scaling harder. Rather vertical scaling makes sense. However if we use NoSQL it is easier to scale Horizontally.

**Reliability or ACID Compliancy (Atomicty, Consistency, Isolation, Durabbility)**

The vast majoirty of RDBMS is ACID compliant but NoSQL sacrifice ACID compliance for performance and scalability

## SQL vs NoSQL - Which one to use?

### Reasons to use SQL

**ACID COMPLIANCE**

Atomicity is that each transaction should be indivisible. If even one of the transaction does not occur, it should not occur at all.

Consistency enforces the data to be manipulated only the certain way, the right way.

Isolation makes each transaction independent of each other

Durability denotes transaction's ability to leave a trace

1. If we need to ensure ACID compliance we go with SQL. (e.g E commerce, Fin tech)
2. If your data is structure and robust in design. If you are less dynamic I supposed in traffic and data format

### Reasons to use NoSQL database

1. Storing large amount of data without much structure
2. Making the most of cloud computing and storage
3. Rapid development
