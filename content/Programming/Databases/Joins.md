## INNER JOIN

* An INNER JOIN is a type of JOIN operation in SQL that combines rows from two or more tables based on a related column between them.
* **Matching Records Only:** It returns only the rows where there is a match in **both** tables based on the specified join condition. Rows that do not have a corresponding match in the other table are excluded from the result set.
* **Syntax:**
    ```sql
    SELECT columns
    FROM TableA
    INNER JOIN TableB
    ON TableA.matching_column = TableB.matching_column;
    ```
    * `TableA` and `TableB`: The two tables you want to join.
    * `matching_column`: The column(s) that are common to both tables and used to establish the link (often a foreign key in one table referencing a primary key in another).
* **Purpose:** INNER JOINs are used when you want to retrieve data that exists in both of the tables being joined. For example, if you have a `Customers` table and an `Orders` table, an INNER JOIN can show you all customers who have placed at least one order.
* **Example:** To get the names of customers and the details of their orders, you would use an INNER JOIN:
```sql
SELECT Customers.CustomerName, Orders.OrderID, Orders.OrderDate
FROM Customers
INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```

This query would only return customers who have placed orders and the corresponding order details. Customers who have not placed any orders would not appear in the result, nor would orders that aren't linked to a valid customer.