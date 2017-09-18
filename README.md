## Liberty App Accelerator
This project was generated by the [Liberty app accelerator](http://ibm.biz/appaccelerator)

[![](https://img.shields.io/badge/bluemix-powered-blue.svg)](https://bluemix.net)
[![Platform](https://img.shields.io/badge/platform-java-lightgrey.svg?style=flat)](https://www.ibm.com/developerworks/learn/java/)

### Table of Contents
* [Summary](#summary)
* [Requirements](#requirements)
* [Configuration](#configuration)
* [Project contents](#project-contents)
* [Run](#run)
* [Notices](#notices)

### Summary

The Liberty App Accelerator provides a starting point for creating applications running on [WebSphere Liberty](https://developer.ibm.com/wasdev/).

To deploy this application to Bluemix using a toolchain click the **Create Toolchain** button.
[![Create Toolchain](https://console.ng.bluemix.net/devops/graphics/create_toolchain_button.png)](https://console.ng.bluemix.net/devops/setup/deploy/)

### Requirements
* [Maven](https://maven.apache.org/install.html)
* Java 8: Any compliant JVM should work.
  * [Java 8 JDK from Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
  * [Java 8 JDK from IBM (AIX, Linux, z/OS, IBM i)](http://www.ibm.com/developerworks/java/jdk/),
    or [Download a Liberty server package](https://developer.ibm.com/assets/wasdev/#filter/assetTypeFilters=PRODUCT)
    that contains the IBM JDK (Windows, Linux)

### Configuration
The application is configured to provide various technologies and features. These capabilities are provided through dependencies in the pom.xml file and Liberty features enabled in the server config file found in `src/main/liberty/config/server.xml`.

### Project contents
The context root is set in the `src/main/webapp/WEB-INF/ibm-web-ext.xml` file. The ports are set in the pom.xml file.     

* **Springboot** : Inside the project there is a application.springboot.web package containing two classes:
    * `SpringBootLibertyApplication`: The entry point for the SpringBoot application.
    * `LibertyHelloController`: A Spring REST endpoint which you can access at `http://localhost:9080/<context>/springbootweb`

There is also a test class named `it.springboot.web.HelloControllerTest` that will test the Spring REST endpoint to ensure it is working.  

* **Watson SDK** : The Watson SDK provides an API for accessing Watson Services. For the complete documentation, take a look at [the Watson developer pages](https://developer.ibm.com/watson/) and [the Watson SDK github project](https://github.com/watson-developer-cloud/java-sdk).  

The project contains Bluemix specific files that are used to deploy the application as part of a Bluemix DevOps flow. The `.bluemix` directory contains files used to define the Bluemix toolchain and pipeline for your application. The `manifest.yml` file specifies the name of your application in Bluemix, the timeout value during deployment and which services to bind to.

### Run

To build and run the application:
1. `mvn install`
1. `mvn liberty:run-server`
 

To deploy the application to bluemix:
1. `mvn install -Pbluemix -Dcf.org=[your email address] -Dcf.username=[your username] -Dcf.password=[your password]`

The application will be deployed to the following url: [http://LibertyProject.mybluemix.net/LibertyProject/]

Alternatively use the Toolchain button above.

### Endpoints

The context root is set in the `src/main/webapp/WEB-INF/ibm-web-ext.xml` file. The ports are set in the pom.xml file.

### Notices

This project was generated using:
* generator-java v2.2.1
* java-common v2.2.0
* generator-ibm-service-enablement v^0.0.59
* generator-ibm-cloud-enablement v^0.0.68
* generator-liberty v5.2.0
