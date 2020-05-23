# 🔥Code Secrets

<img src="./assets/images/secrets.png" alt="secrets" width="700">

!> Don't share application credentials to anyone nor commit them to Github commits.

?> Credentials are usually hidden in environment variables that your application can pick up when it runs. On the command-line, environment variables can be set using **export** on Mac/Linux and **set** on Windows

```bash
export MYAPIKEY=ndsvn2g8dnsb9hsg
```

> A simple way of defining multiple environment variables on your local machine is to use the [dotenv](https://www.npmjs.com/package/dotenv) package. Create a **.env** file at the top of your project containing the environment variables you want to set:

```bash
MYAPIKEY=ndsvn2g8dnsb9hsg 
DEBUG=true 
DEBUGLEVEL=5
```

Then at the entry point in your code add and this will make sure to load the values from the **.env file** into your application's **process.env**.

```bash
require('dotenv').config();
```
