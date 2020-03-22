+++
title = "Spring Boot Documentation"
menutitle = "Spring MVC"
description = "Spring MVC"
weight = 2
+++

## **Spring Boot Documentation**

---

## Things to know

- Spring Initializr: Fast way to pull in dependencies you need for an application and does most of the work for you.
  - Example dependencies:
    1. Spring Web:
    1. Thymeleaf
    1. Spring Boot DevTools

- Maven comes with a `pom.xml` file
- Gradle comes with the `build.gradle` file
- Language is chosen with an 'id' (i.e. "`id 'java'`") (done under plugins)
- Spring framework & dependency management are also under plugins.

---

## Terms (of options)

- Group: Project Coordinates; `id` of the project's group; Infers Root package name;
- Artifact: Project Coordinates; `id` of the Artifact; Infers name of project;
- Name: Display Name of Project; Determines name of Spring Boot Application;
- Description: Description of project;
- Package name: Root package of the project; Default is [`Group`]() attribute;
- Packaging: Project Packaging; Either Java Archive (**JAR**) or Web Application Archive (**WAR**);
- Java Version: Which version of Java to use;
- Language: Which programming language to use;

---

## Web Controllers

HTTP(S) requests are handled by a controller.
