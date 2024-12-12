# maven-build
for building a simple maven application


# Install Maven 
    -  sudo apt install -y maven

## verify Maven Version 
    - mvn -version



# Create Java Projects using the [maven-archetype](https://maven.apache.org/guides/introduction/introduction-to-archetypes.html). 


## 1 Generate a Simple Java App (JAR) project

Use the below command to generate a standard project structure Template for a maven build project. 

    - mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5 -DinteractiveMode=false

cd into the my-app directory generated by previous command

    - cd my-app

type tree command to see the standard folder structure of  a maven project. If not present, install linux tree command

    - tree

This should display the folder struture

![alt text](image.png)

The **src/main/java** directory contains the project source code, the **src/test/java** directory contains the test source, and the **pom.xml** file is the project's Project Object Model, or POM.


## 2 Generate a Web (WAR) Project 
 Run the below command to generate a Web App project

    - mvn archetype:generate -DgroupId=com.jjtech -DartifactId=JJtechBatchApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false

The above command will generate a standard maven project template for a simple Web application 

    