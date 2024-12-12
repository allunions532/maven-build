# maven-build
for building a simple maven application


# Install Maven 
    -  sudo apt install -y maven

## verify Maven Version 
    - mvn -version



# Create Java Projects using the [maven-archetype-webapp](https://maven.apache.org/guides/introduction/introduction-to-archetypes.html). 


## 1 Generate a Simple Java App (JAR) project
    - mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5 -DinteractiveMode=false

cd into the my-app directory generated by previous command
    - cd my-app

    type tree command to see the standard folder structure of  a maven project. If not present, install tree
    
    - tree


## 2 Generate a Web (WAR) Project 
 Run the below command to generate a Web App project

    - mvn archetype:generate -DgroupId=com.jjtech -DartifactId=JJtechBatchApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false

The above command will generate a standard maven project template for a simple Web application 

    