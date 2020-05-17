# 🔥 Redis

> Redis is a NoSQL(**‘Not only SQL’**) and it is an in-memory database (**IMDB**).

## ⚡in-memory Database

<img src="./assets/images/imdb.png" alt="imdb" width="700">

?> An **in-memory database (IMDB)** is a database management system that primarily relies on main memory for computer data storage. It is contrasted with **database management systems(MySQL, PostgreSQL) that employ a disk storage mechanism**. In-memory databases are faster than disk-optimized databases because disk access is slower than memory access, the internal optimization algorithms are simpler and execute fewer CPU instructions. Accessing data in memory eliminates seek time when querying the data, which provides faster and more predictable performance than disk.

[🌐 More about IMDB](https://en.wikipedia.org/wiki/In-memory_database)

## ⚡Classification of NoSQL Databases

<img src="./assets/images/classification_nosql.jpg" alt="types of nosql" width="700">

## ⚡How to install Redis on Windows

* Download latest **redis.msi** file from [microsoftarchive/redis](https://github.com/microsoftarchive/redis/releases).
* Above step will make sure that **Redis** is installed on your machine as Service and Path variable is updated with your **Redis PATH**.
* You can switch on and off your **Redis Server** from your **Windows Services** App.
* You can install Redis GUI called [RedisInsight](https://redislabs.com/redisinsight/) to access Redis Database.
* Default Port on which Redis is accessed : **6379**

[🌐 Redis Setup Documentation](https://medium.com/@mayank_goyal/how-to-install-redis-and-as-a-windows-service-f0ab2559a3b)

## ⚡Redis Commands

* [Redis DataTypes](https://redis.io/topics/data-types-intro)
* [DataType Strings in Redis](https://redislabs.com/ebook/part-1-getting-started/chapter-1-getting-to-know-redis/1-2-what-redis-data-structures-look-like/1-2-1-strings-in-redis/)
* [Hashes in Redis](https://redislabs.com/ebook/part-1-getting-started/chapter-1-getting-to-know-redis/1-2-what-redis-data-structures-look-like/1-2-4-hashes-in-redis/)
* [Lists in Redis](https://redislabs.com/ebook/part-1-getting-started/chapter-1-getting-to-know-redis/1-2-what-redis-data-structures-look-like/1-2-2-lists-in-redis/)
* [Sets in Redis](https://redislabs.com/ebook/part-1-getting-started/chapter-1-getting-to-know-redis/1-2-what-redis-data-structures-look-like/1-2-3-sets-in-redis/)

> [🌐 List of all Commands](https://redis.io/commands)

> [▶ Tutorial to learn essential Redis Commands](https://www.youtube.com/watch?v=Hbt56gFj998)

## ⚡How IMDB used in Realworld applications?

<img src="./assets/images/imdb1.png" alt="imdb1" width="700">

> User data is stored in main memory of our machine on successful user requests. All user transactions are stored in **Transaction Log**.

<img src="./assets/images/imdb2.png" alt="imdb2" width="700">

> After specified amount of time, all user transactions are persisted in databases(MySQL, PostgreSQL) that use disk storage. In this way we can use in-memory databases to persists data efficiently.

[🌐 Reference](https://medium.com/@denisanikin/what-an-in-memory-database-is-and-how-it-persists-data-efficiently-f43868cff4c1)

[🌐 Redis application caching](https://redislabs.com/redis-enterprise/use-cases/caching/)

[🌐 Redis Session Management](https://redislabs.com/redis-enterprise/use-cases/session-management/)

[▶ How to Cache web application using Redis](https://www.youtube.com/watch?v=oaJq1mQ3dFI)