# Schemas and Relationships research

![database](http://s2.quickmeme.com/img/38/3821733495c7e958cbfbc8dd14335f67d4396da8b8b8f0032d9bc5f45ff3c794.jpg)

## We will discuss the following topics:
  * What is a **schema** and why/when would you need one?

* What are **primary keys** and why do we need them?

* Create a visual representation of a mock schema for a database about Founders & Coders, using as many different kinds of relationship as you can. Explain the logic behind it.
___
### what is schema ?
Schema refers to the organization of data, or schema is the structure of the database that defines the objects in the database.

This describes how **real-world** entities are modeled in the database.

In a relational database, the schema defines the **tables**, **fields**, **relationships**, **views**, and so on.

### Why we use schema
* security management , define who can access and which database objects.

* serve as a namespace, that is preventing name crash between objects from different schemas.

___

A **Primary Key** is a special relational database table column (or combination of columns) used to uniquely identify all table records.

 ### it has the following properties:



* Primary keys must contain UNIQUE values, and cannot contain NULL values.

* A table can have only one primary key, which may consist of single or multiple fields.

### Primary key constraint:

```
CREATE TABLE Persons (
  ID int NOT NULL PRIMARY KEY,
);

```
### Foreign Key ? :worried:
>A **foreign key** is a set of one or more columns in a table that refers to the primary key in another table.

**Persons Table**


PersonID | FirstName | LastName
------------ | ------------- |-------------
1 | Mahmoud | Al-Madhoun
2 | Abdallah | Al-Halees

**Orders Table**


OrderID | OrderNumber | PersonID
------------ | ------------- | -------------
1 | 3212 | 1
2 | 3213 | 2


>The "PersonID" column in the "Persons" table is the PRIMARY KEY in the "Persons" table.

>The "PersonID" column in the "Orders" table is a FOREIGN KEY in the "Orders" table.






___


### F & C Database Schema
A visual representation of a mock schema for a database about Founders & Coders.
A simple database will have cohorts and students who has been in a cohort and mentors who has been graduated from cohorts and a team who manages the organization.

Cohorts has no direct relationship with other tables but students has to have a cohort, and mentors has to have a cohort that he graduated from and the cohort that he is mentoring.


### Cohorts - `cohorts`

Column | Type | Modifiers
--- | --- | ---
id | SERIAL | PRIMARY KEY
location_id | INTEGER | REFERENCES location(id)
number | INTEGER | NOT NULL
start\_date | VARCHAR(50) | NOT NULL
end\_date | VARCHAR(50) | NOT NULL





### Students - `students`

Column | Type | Modifiers
--- | --- | ---
id | SERIAL | PRIMARY KEY
name | VARCHAR(30) | NOT NULL
email | VARCHAR(30) | NOT NULL
cohort | INTEGER | REFERENCES cohorts(id)
github_account | VARCHAR(20) | NOT NULL
brithday | VARCHAR(30) | NOT NULL
T-shirt_size | VARCHAR(30) |
mobile | INTEGER |
address | VARCHAR(30) |



### Mentors - `mentors`

Column | Type | Modifiers
--- | --- | ---
id | SERIAL | PRIMARY KEY
students\_id | INTEGER | REFERENCES students(id),
mentors\_at | INTEGER | REFERENCES cohorts(id),
week | INTEGER |




### Staff - `staff`

Column | Type | Modifiers
--- | --- | ---
id | SERIAL | PRIMARY KEY
name | VARCHAR(20) | NOT NULL
email | VARCHAR(20) | NOT NULL
github_account | VARCHAR(20) | NOT NULL
role | VARCHAR(100) | NOT NULL
location_id | INTEGER | REFERENCES location(id)


### Location - `location`

Column | Type | Modifiers
--- | --- | ---
id | SERIAL | PRIMARY KEY
name | VARCHAR(20) | NOT NULL



___
**Resources:**

* [What Is a Schema?
](http://www.informit.com/articles/article.aspx?p=1216889&seqNum=2)
* [W3School](https://www.w3schools.com/sql/sql_primarykey.asp)
* [What is the Difference between a Primary Key and a Foreign Key?](https://www.essentialsql.com/what-is-the-difference-between-a-primary-key-and-a-foreign-key/)
