# 🔥CI/CD

<img src="./assets/images/cicd.png" alt="CICD" width="700">

### ✳Continuous Integration (CI)

<img src="./assets/images/cicd_3.png" alt="CICD" width="700">

?> **Continuous Integration (CI)** is a development practice where developers integrate code into a shared repository frequently, preferably several times a day. Each integration can then be verified by an automated build and automated tests. While automated testing is not strictly part of CI it is typically implied.

?> One of the key benefits of integrating regularly is that you can **detect errors quickly and locate them more easily**. As each change introduced is typically small, pinpointing the specific change that introduced a defect can be done quickly.

<img src="./assets/images/cicd_2.png" alt="CICD" width="700">

?> In the above figure we are implementing following steps in Continuous Integration pipeline:

1. Using Typescripy for strict typing and writing test cases for our scripts.
2. Formatting our code against our common coding standard rules.
3. Push our changes to Version Control hub(Github) to create Pull Request(PR).
4. Step 3 will trigger **CI** and in this step it will check success for pre defined rules(success of test cases, static analysis of code etc.,)
5. On success of Step 4, PR is created and send that PR for code review.
6. After success of Step 5, all changes from developer are merged into master branch.

> [🌐 Top 8 Continuous Integration Tools](https://code-maze.com/top-8-continuous-integration-tools/)

### ✳Continuous Delivery (CD)

<img src="./assets/images/cicd_4.png" alt="CICD" width="700">

?> **Continuous Delivery** is the practice of keeping your codebase deployable at any point. Beyond making sure your application passes automated tests it has to have all the configuration necessary to push it into production. Many teams then **do push changes that pass the automated tests** into a test or production environment immediately to ensure a fast development loop.

### ✳Continuous Deployment (CD)

<img src="./assets/images/cicd_5.png" alt="CICD" width="700">

?> **Continuous Deployment** is closely related to Continuous Integration and refers to keeping your application deployable at any point or even **automatically releasing to a test or production environment** if the latest version passes all automated tests.

### ✳Complete Setup of CI/CD pipeline

<br>

<img src="./assets/images/cicd_6.png" alt="CICD" width="700">
