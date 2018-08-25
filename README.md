# Spring Boot RESTful API - JPA Hibernate MySQL Example #

&nbsp;

RESTful API using Spring Boot, Swagger2, JPA hibernate and Mysql, One to Many, Many to One bidirectional mapping

&nbsp;

## Relation ## 

![image](https://user-images.githubusercontent.com/28649770/44622337-69c67a80-a8f1-11e8-99d7-34adb90779a3.png)

&nbsp;

### Bidirectional Mapping ### 

* Project - Problem (One-To-Many)
* Problem - Project (Many-To-One)

* Problem - SubProblem (One-To-Many)
* SubProblem - Problem (Many-To-One)

&nbsp;

## RESTful API Server ##

&nbsp;
**API Description for Project**

METHOD | PATH | DESCRIPTION 
------------|-----|------------
GET | /api/project/{code} | get Project-Problem-SubProblem with code
POST | /api/project | save Project (code will generate by constructor) 
DELETE | /api/project/{code} | delete Project with code
PUT | /api/project/{code} | update Project with code

**API Description for Problem & SubProblem**

METHOD | PATH | DESCRIPTION 
------------|-----|------------
GET | /api/problem/{code} | get all Problem-Subproblem with code
POST | /api/problem/{code} | save Problem with code
DELETE | /api/problem/{code}/all | delete all Problem-Subproblem with code
POST | /api/subproblem | save Subproblem

## Running the project with MySQL ##

append this at the end of application.yml

```yml
spring:
    application:
      name: project-api
       
## Hibernate Properties
# The SQL dialect makes Hibernate generate better SQL for the chosen database
    jpa: 
      properties:
        hibernate:
          dialect: org.hibernate.dialect.MySQL5InnoDBDialect
      hibernate:
        ddl-auto: update
        # Hibernate ddl auto (create, create-drop, validate, update)
      
    datasource:
      url: jdbc:mysql://{YOUR_MSQL_SERVER}:3306/{DATABASE NAME}?useSSL=false
      username: {YOUR_MYSQL_ID}
      password: {YOUR_MYSQL{PASSWORD}
      driver-class-name: com.mysql.jdbc.Driver
      hikari:
        maximum-pool-size: 2
```



## Swagger ## 

You can use the Swagger API Documentation at http://{Your_Server}:{Port}/swagger-ui.html

![image](https://user-images.githubusercontent.com/28649770/44622453-8bc0fc80-a8f3-11e8-9223-b5a21717ba6d.png)
