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

* Your client would like you to provide a basic asset register. An asset consists of atleast a description, 
  the base cost of the asset and the current value of the asset after depreciation. To achieve this you need to implement a simple database system that implements 
  basic CRUD operations via RESTful endpoints.

```

@Repository
public interface AssetRepository {
    public List<Asset> getAssets();
    public List<Asset> getAssetsByDescription(String description);
    public List<Asset> getAssetsByValue(double value);
    public Asset getAssetById(Long id);

    public Long addAsset(Asset asset);
    public void updateAsset(Long id, Asset asset);

    public void deleteAssetById(Long id);
}

```
 
* The functionality of the repository must be exposed via REST calls. 
* Your client would like you to prevent the user from adding assets with empty descriptions, negative cost and negative current values.
* For convenience your client would like to be able to do asset depreciation on existing assets through the rest interface. 
  The user should be able to pass both the yearly rate of depreciation as a number with range [0,1] and the number of years that have 
  passed to your service. An asset cannot be worth less than 1 rand.
  
  A=C*(1-R)^N
  A->Actual value
  C->Base cost
  R->Depreciation rate
  N->Number of years
  
* Data validation and business rules should be implemented at the service layer.
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
* Fork the *RESTTemplate* project <https://github.com/IMQS/RESTTemplate.git> - use the `master` branch. This project provides a skeleton for service development.
* It can be run on its own but really doesn't do much. See the README.md file in that project.
* Create am IntelliJ project from the POM file and get going!


