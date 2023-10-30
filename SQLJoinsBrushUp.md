# SQL Joins: A Comprehensive Guide

## Introduction to Joins
SQL joins are used to combine records from two or more tables based on a related column. This allows for a more complex and detailed query, enabling the extraction of relational data.
- **Purpose**: Joins help in retrieving data from multiple tables, thus providing a holistic view.
- **Core Concept**: At least one column, usually an ID or a key, should be common in the tables being joined.

## Inner Join (or simply JOIN)
The most common type of join is the Inner Join which returns rows when there is a match in both tables.
- **Result**: Only rows with matching values in both tables are returned.
- **Usage**: Ideal when you only want to retrieve records common to both tables.

For instance, when joining a table of `employees` with a table of `departments`, an Inner Join will return only those employees who are assigned to a department.

## Left Join (or LEFT OUTER JOIN)
A Left Join returns all the rows from the left table, and the matched rows from the right table. If there's no match, the result is `NULL`.
- **Result**: All records from the left table and matched records from the right.
- **Usage**: Useful when you want all records from the left table irrespective of whether they have a counterpart in the right table.

If you had a table of `students` and a table of their `course_enrollments`, a Left Join would list all students and the courses they're enrolled in. Students not enrolled in any course would still be shown, but their course details would be `NULL`.

## Right Join (or RIGHT OUTER JOIN)
The Right Join is essentially the opposite of the Left Join. It retrieves all rows from the right table and the matched rows from the left.
- **Result**: All records from the right table and matched records from the left.
- **Usage**: Less common than Left Join, but useful when prioritizing data in the right table.

Using the previous example of `students` and `course_enrollments`, a Right Join would list all courses and any students enrolled in them. Courses without enrolled students would still be displayed, but student details would be `NULL`.

## Full Outer Join (or FULL JOIN)
A Full Outer Join returns all rows when there is a match in one of the tables. Essentially, it combines the results of both Left and Right Joins.
- **Result**: All records when there's a match in one of the tables.
- **Usage**: When you want to see all records from both tables and easily identify unmatched records.

## Self Join
A self join combines a table with itself. It's useful for extracting hierarchical data from a single table.
- **Result**: Data related within the same table.
- **Usage**: Commonly used with tables that have a hierarchical structure, like an `employees` table where one employee can report to another.

## Cross Join
A cross join returns the Cartesian product of the two tables, meaning every row from the first table is combined with every row from the second table.
- **Result**: Combines each row of the first table with each row of the second table.
- **Usage**: Used carefully, as it can result in very large datasets. Often used when you want to combine all possible combinations of two sets of data.

## Conclusion:
Joins are an essential tool in SQL, allowing for complex queries across multiple tables. Understanding the different types of joins and their applications ensures that you can retrieve data efficiently and effectively, catering to various data analysis requirements.


# Multiple Choice Quiz Questions:

### Theory Question:
In which type of join would you retrieve all records from both tables, including those that don't have a counterpart in the other table?
- a) Inner Join
- b) Left Join
- c) Right Join
- d) Full Outer Join

### Scenario-Based:
If you have a table `authors` and another table `books`, and you want to list all authors, including those who haven't written any book, which join would you use?
- a) Self Join
- b) Cross Join
- c) Left Join (with `authors` as the left table)
- d) Right Join (with `books` as the right table)

### True or False:
A Right Join retrieves all rows from the right table and only the matched rows from the left table.

### Application Question:
Which type of join would you use if you want to show the hierarchy within an `employees` table, where one employee can report to another?
- a) Cross Join
- b) Self Join
- c) Inner Join
- d) Full Outer Join

### Theory Question:
Which type of join results in the Cartesian product of the two tables?
- a) Inner Join
- b) Left Join
- c) Cross Join
- d) Self Join

### Scenario-Based:
If you want to retrieve data that only exists in both tables, ensuring there are no NULL values in the columns from either table in the result, which join would you use?
- a) Left Join
- b) Right Join
- c) Inner Join
- d) Full Outer Join

# SQL Code Based Questions:

1. Given two tables, `students` and `courses`, write an SQL statement to list all students and the courses they're enrolled in, even if they're not enrolled in any course.

2. Consider a table named `employees` with a self-referencing column `manager_id`. Write an SQL statement to list all employees alongside the names of their respective managers.

3. An `orders` table exists with columns for order details and a `customer_id`. Another table, `customers`, contains customer details. Write an SQL query to retrieve all customer names, even if they haven't placed any orders.

4. The table `projects` lists all ongoing projects, and another table `team_members` lists employees assigned to each project by `project_id`. If you want a list of all projects and their team members (if any), which SQL statement would you write?

5. You spot the following SQL query in a colleague's code:
```sql
SELECT products.name, suppliers.name
FROM products
RIGHT JOIN suppliers ON products.supplier_id = suppliers.id;
```

6. What will this query retrieve and how could it be modified to retrieve all products, even if they don't have a supplier?

7. Write an SQL statement that retrieves the combination of every product with every category from the products and categories tables respectively.


