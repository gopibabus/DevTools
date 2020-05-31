# 🔥Database Scaling

<img src="./assets/images/db_scaling.png" alt="db scaling" width="500">

## ⚡Ways to scale a given database:

### ✳Identify inefficient queries.

> We can handle ineffecient queries in 2 ways:

- Requesting only the data we needed for a given operation.
- [Indexing database](https://www.tutorialspoint.com/mysql/mysql-indexes.htm)

### ✳Increase Memory

?> ⭐ In this method, we increase memory(RAM) of the database server.

### ✳Vertical Scaling (Redis, Memchached)

?> Following diagram depicts how **Swiggy** using Redis in **vertical scaling** their MySQL Database.

<img src="./assets/images/vertical_scaling.png" alt="vertical scaling" width="700">

### ✳Sharding

?> **Sharding** is a database architecture pattern related to **horizontal partitioning** — the practice of separating one table’s rows into multiple different tables, known as partitions. Each partition has the same schema and columns, but also entirely different rows. Likewise, the data held in each is unique and independent of the data held in other partitions.

<img src="./assets/images/db_shrading.png" alt="db_shrading" width="700">

### ✳More Databases

?> In this method we employ multiple databases with same data. **Load balancer** is used in our application to redirect user requests to multiple databases using load balancer.

<img src="./assets/images/more_db.png" alt="more db" width="700">

### ✳Database Type

?> Different databases are best in handling different types of tasks. So in our application we should use different databases like MongoDB, MySQL etc., to handle different type of tasks.

<img src="./assets/images/sql_nosql.png" alt="sql nosql" width="700">
