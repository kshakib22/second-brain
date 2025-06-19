
**Primary Key:**

* A primary key is a column or a set of columns in a database table that uniquely identifies each row in that table.
* **Uniqueness:** No two rows can have the same primary key value.
* **Non-nullability:** A primary key column cannot contain NULL values; it must always have a value.
* **Purpose:** Its main purpose is to provide a unique identifier for each record, making it easy to retrieve, update, or delete specific rows. It also serves as the "anchor" for relationships with other tables.
* **Example:** In a `Customers` table, `CustomerID` would typically be the primary key. Each customer will have a unique `CustomerID`, and this field will not be empty.

**Foreign Key:**

* A foreign key is a column or a set of columns in a database table that refers to the ==primary key in another table==.
* **Relationship:** It establishes a link or relationship between two tables. The table containing the foreign key is called the "child table," and the table containing the primary key (to which the foreign key refers) is called the "parent table."
* **Referential Integrity:** Foreign keys enforce referential integrity, meaning that if a foreign key value exists in the child table, its corresponding primary key value must also exist in the parent table. This prevents "orphan" records and ensures data consistency.
* **Purpose:** Foreign keys are used to connect related data across different tables. For instance, to find all orders placed by a specific customer, you would use the foreign key in the `Orders` table that links back to the primary key in the `Customers` table.
* **Example:** In an `Orders` table, `CustomerID` would likely be a foreign key that references the `CustomerID` primary key in the `Customers` table. This allows each order to be associated with a specific customer.

In essence, the primary key identifies records within its own table, while the foreign key links records from one table to records in another, creating a structured and interconnected database.