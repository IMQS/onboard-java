# onboard-java
Onboarding project for Java
===========================

This is a Java project that all new developers must complete. The primary focuses is on REST APIs and using the Spring Framework as a basis for service implementations.

After completing this project you should have a basic understanding of:
 
* How Spring dependency injection works
* Configuring Spring using `Annotations`
* How to access a SQL database with Spring `JdbcTemplate`
* The IMQS service skeleton that we use to build our web services

What you need to do
-------------------

* You need to implement a simple database system that implements basic CRUD operations via RESTful endpoints.  Your service must have a repository implementation that implements the interface `PeopleRepository`.

```
public interface PeopleRepository {
    public interface Person {
        public String getFirstName();
        public String getSurname();
        public void setFirstName(String firstName);
        public void setSurname(String surname);
    }

    public List<Person> getPeople();
    public List<Person> getPersonByName(String name);
    public List<Person> getPersonBySurname(String name);
    public Person getPersonById(Long id);

    public Long addPerson(Person person);
    public void updatePerson(Long id, Person person);

    public void deletePersonById(Long id);
}
```
 
* The functionality of the repository must be exposed via REST calls. 
* You must write unit tests using JUnit. 
* You must be able to deploy and run the service on your machine - i.e. as a windows service.
* You must be able to run the service from your IDE
* You must be able to single step through your service using the IDE's built in debugger
 
Pre-requisites
----------------

To get started you will need to familiarise yourself with the basic concepts behind Spring. <http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/>.  
You are encouraged to read the entire document, but pay specific attention to chapters:

* 2.1 - Dependency Injection and Inversion of Control
* 6.1 - Introduction to the Spring IoC container and beans
* 6.2 - Container overview
* 6.3 - Bean Overview
* 6.4 - Dependencies
* 6.9 - Annotation-based container configuration
* 6.12 - Java-based container configuration

Also you will need to have completed your environment setup. At the very least you need to have IntelliJ running, have maven configured and have GIT working.

Getting started
----------------
* Fork the *RESTTemplate* project - use the `master` branch. THis project provides a skeleton for service development
* It can be run on its own but really doesn't do much. See the README.md file in that project.
* Create am IntelliJ prokject from teh POM file and get going!


