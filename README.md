# Spring Boot RESTful API - JPA Hibernate MySQL Example #

RESTful API using Spring Boot, Swagger2, JPA hibernate and Mysql, One to Many, Many to One bidirectional mapping

## Relation ## 

![image](https://user-images.githubusercontent.com/28649770/44622337-69c67a80-a8f1-11e8-99d7-34adb90779a3.png)

### Bidirectional Mapping ### 

* Project - Problem (One-To-Many)
* Problem - Project (Many-To-One)

* Problem - SubProblem (One-To-Many)
* SubProblem - Problem (Many-To-One)

&nbsp;
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


