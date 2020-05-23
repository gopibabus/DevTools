# 🔥Injection Attacks

> **Injection attacks** is the attack that allow an attacker to supply **untrusted input** to a program, which gets **processed by an interpreter as part of a command or query** which alters the course of execution of that program. They can result in data theft, data loss, loss of data integrity, denial of service, as well as full system compromise.

!> It is listed as the **number-one web application security risk** in the OWASP Top 10

?> There are various types of injection attacks. Important among them is **SQL injection** and **Cross-site scripting**.

### ✳SQL injection (SQLi)

> **SQL injection** that allows an attacker to interfere with the queries that an application makes to its database. It generally allows an attacker to view data that they are not normally able to retrieve. This might include data belonging to other users, or any other data that the application itself is able to access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior.

<img src="./assets/images/sql-injection.svg" alt="sql-injection" width="700">

?> [Playground to try SQL Injection](https://www.hacksplaining.com/exercises/sql-injection)

### ✳cross-site scripting (XSS)

> **Cross-site scripting (also known as XSS)** is a web security vulnerability that allows an attacker to compromise the interactions that users have with a vulnerable application. Cross-site scripting works by manipulating a vulnerable web site so that it returns malicious JavaScript to users. When the malicious code executes inside a victim's browser, the attacker can fully compromise their interaction with the application.

<img src="./assets/images/cross-site-scripting.svg" alt="cross-site-scripting" width="700">

### ✳Other forms of injection attacks

* Code injection
* CRLF injection
* Email Header Injection
* Host Header Injection
* LDAP Injection
* OS Command Injection
* XPath injection etc.,

### ✳How to avoid injection attacks?

**Sanitize Input**

?> Input sanitization describes cleansing and scrubbing user input to prevent it from jumping the fence and exploiting security holes.

**Parametrize Queries**

?> A parameterized query (also known as a prepared statement) is a means of pre-compiling a SQL statement so that all you need to supply are the "parameters" (think "variables") that need to be inserted into the statement for it to be executed. It's commonly used as a means of preventing SQL injection attacks.

> Example: [knex.js](http://knexjs.org/) and Other [ORMs](https://www.doctrine-project.org/)