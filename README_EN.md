# Tech Stack

1. **`Java`**
2. **`Spring`**, **`Spring Boot`**
3. **`JPA`**, **`Spring Data JPA`**
4. **`MariaDB`**, `Mysql`
5. `Servlet` & `JSP`

# Work Experience

| Year         | Activity                                                                                      |
|--------------|-----------------------------------------------------------------------------------------------|
| 2024 - Present | Woowa Tech Course, 6th Backend Developer Training Program                                    |
| 2022         | [Goal-achievement-system](https://github.com/Goal-achievement-system) Backend Developer        |
| 2022         | [Great-Student-Manage-System](https://github.com/Great-Student-Manage-System) Backend Developer|
| 2020 - 2021  | Developed the homepage for the HUST Information Security Club at Hongik University            |
| 2018         | Vice President of the HUST Information Security Club at Hongik University                     |
| 2016 - 2023  | Member of the HUST Information Security Club at Hongik University                             |
| 2016 - 2023  | Studied Computer and Information Communications Engineering at Hongik University              |

# Project List

## GoalKeeper

This is the GoalKeeper project, a system to motivate users in achieving their goals.

**Key Technologies**: **`Spring Interceptor`, `ExceptionHandler`**

Repository: [Goal-achievement-system/backend](https://github.com/Goal-achievement-system/backend)

### Tasks

- **Used `Spring Interceptor` for Common Task Processing**
    - Since user authentication using Access Tokens is required for almost all features, `Spring Interceptor` was used to execute this task before any controller operations.
  
- **Solved CORS Configuration Issues in `Spring Interceptor` and `Spring WebMvcConfigurer`**
    - Faced issues with CORS settings not working as expected.
    - By deeply studying CORS and analyzing packets with BurpSuite, discovered that the problem was caused by improperly handled preflight requests.
    - Identified that the Access Token handling interceptor was mistakenly trying to extract tokens from preflight requests and resolved this by applying an exception handling mechanism.
    - Details can be found in [this blog post](https://www.notion.so/CORS-a320cfb895234bdeb8cc5e7248ac65a2).
  
- **Reduced Duplicate Exception Handling with `ExceptionHandler`**
    - There were repeated try-catch blocks in controllers, affecting readability and increasing potential for errors.
    - Abstracted exception handling and used **`ExceptionHandler`** to separate exception processing tasks from controllers.

## GoalKeeper 2

This project extends the original GoalKeeper project by applying new features and technologies.

**Key Technologies**: **`Spring Data JPA`, `GitHub Actions`, `Servlet Filter`, `Spring AOP`, `Spring Interceptor`**

Repository: [GoalKeeperV2-backend](https://github.com/GoalKeeperV2-0/GoalKeeperV2-backend-)

### Tasks

- **Built a Logging System using `Servlet Filter`, `Spring AOP`, `Spring Interceptor`**
    - The original version lacked logging, making it hard to trace errors when adding new features.
    - Set up a logging system using **`Servlet Filter`**, **`Spring AOP`**, and **`Spring Interceptor`**.
    - Detailed learning process documented in [this blog post](https://www.notion.so/Spring-Boot-REST-API-System-Logging-6a833112c36b4482855de067b255e1c7).

- **Implemented `Spring Data JPA` for an Object-Oriented Design**
    - Previous version used JdbcTemplate, embedding SQL statements directly, which often buried business logic in SQL.
    - Used **`Spring Data JPA`** to keep business logic in entity classes and implement changing operational policies in services.

- **Implemented Automated Deployment using `GitHub Actions`**
    - Previously, deployments required manually connecting to the server and running commands, often leading to issues.
    - Set up **`GitHub Actions`** for CI/CD and automated server deployment, reducing manual errors.

## Great

Great is a student management system designed for small-scale academy instructors.

**Key Technologies**: **`AccessToken`, `RefreshToken`, `Cookie`**

Repository: [Great-Student-Manage-System/Backend](https://github.com/Great-Student-Manage-System/Backend)

### Tasks

- **Used `AccessToken`, `RefreshToken`, `Cookie` for Safer and Convenient Authentication**
    - Implemented **`AccessToken`, `RefreshToken`, `Cookie`** for secure user authentication.
    - Faced an issue where cookies set by the backend weren’t visible in the frontend due to certain cookie attributes.
    - Detailed analysis available in [this blog post](https://www.notion.so/Great-ab2740cf8f6e450684d15e816da65742).

## HUST Website

Developed a homepage for the HUST club.

**Key Technologies**: **`Servlet`, `JSP`, `HTML5`, `Bootstrap`, `Jquery`, `WebSocket`, `JDBC`**

Repository: [HUST_WEB](https://github.com/robinjoon/HUST_WEB)

### Tasks

- **Used `JDBC` for Database Connectivity**
    - Used MariaDB to store data like members, posts, and comments, connecting it with Java through JDBC.

- **Developed Dynamic Web Pages using `Servlet`, `JSP`**
    - Employed **`Servlet`** and **`JSP`** to dynamically display post data.
  
- **Enabled Real-Time Communication with `Jquery` and `WebSocket`**
    - Implemented **`WebSocket`** for real-time server communication with frontend support via **`Jquery`**.

## O’Clock

### Tasks

- **Implemented Chat Functionality with `WebSocket`**
    - Built chat functionality using **`WebSocket`** with **`TextWebSocketHandler`** in **`Spring`**.
  
- **Separated DTO for Sensitive Information Exclusion**
    - Implemented a DTO to prevent sensitive data from being exposed when querying chat participant info.
    - Detailed documentation in [this blog post](https://robinjoon.notion.site/DB-3655ea99edd8413790635d4d3abd5e54).
