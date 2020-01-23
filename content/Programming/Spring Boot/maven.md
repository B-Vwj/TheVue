+++
title = "Spring Boot Documentation"
menutitle = "Maven"
description = ""
weight = 2
+++

## Maven

"When building our Spring Application, we need to manage our dependencies."

"We need to import the 'Jar's that is required for Spring Applications to work."

- Usually in Java, you'd take the **JARs** and add it to the **CLASSPATH**
  - We won't do this. We'll use ***Maven*** instead!

### What is Maven?

Maven: Build Independency Management Tool

Lets you declare all the dependencies you want in a single file.
  - No more needing to download the JARs and adding it into the CLASSPATH.
  - Rather, you mention what JARs you need into the file `pom.xml`.
    - `pom.xml` contains a list of all your dependencies that Maven needs to know/to get
    - After running a Maven cmd, Maven will check what dependencies are needed for the app, and will get the JARs from a Repository.

In short:
1. When needing dependencies, we create the `pom.xml` file.
1. Add a list of dependencies onto the `pom.xml` file.
1. Then run a Maven cmd.

### Extras

Maven also lets you create a starter project. (no need to create this individual files yourself)
- Comes with an 'Archtype' (basically a template) which lets you start a simple project.
  - In other words, Maven basically creates files, including the `pom.xml` file for you to begin listing dependencies you need.
