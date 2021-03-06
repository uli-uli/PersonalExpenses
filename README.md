# Personal Expenses REST Application

Personal expenses REST application based on Spring Boot, Spring data JPA, Maven and H2 in-memory database.


## Contents

1. [Features](#features)
2. [Requirements](#requirements)
3. [How to run the application](#how-to-run-the-application)
4. [POST request example](#post-request-example)


## Features

* Based on Spring boot, Spring data JPA, Maven and H2 in-memory database
* Has following API:
  * PATH (/expenses) `POST` http request — adds expense entry in the database. Endpoint accepts JSON with the following fields: `date, amount, currency, product` 
  * PATH (/expenses) `GET` http request — returns the list of all expenses `grouped and sorted by date`
  * PATH (/expenses?date=YYYY-MM-DD) `DELETE` http request — removes all expenses for specified date, where: `date` - is the date for which all expenses should be removed
  * PATH (/expenses/total?base=UAH) `GET` http request — returns total amount of spent money converted and calculated to specified currency by online converter and presents it in specified currency, where `base` - is the currency in which total amount of expenses should be presented
  * Spring MVC with Service layer and DTO pattern
  * Unit tests
* Input validation of `currency` and `amount` fields


## Requirements

For building and running the application you need:
- [JDK 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Maven 3](https://maven.apache.org)


## How to run the application

There are several ways to run a Spring Boot application on your local machine. One way is to execute the `main` method in the `com.info.personalexpensesapp` class from your IDE.

Alternatively, you can use the [Spring Boot Maven plugin](https://docs.spring.io/spring-boot/docs/current/reference/html/build-tool-plugins-maven-plugin.html) like so:

```shell
mvn spring-boot:run
```

For HTTP requests you can use [Postman](https://www.postman.com/downloads/).


## POST request example:
```
{
"date": "2020-11-02",
"amount": "30",
"currency": "UAH",
"product": "Oranges"
}
```



