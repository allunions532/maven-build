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


## 2 Generate a Web App (WAR) Project 
 Run the below command to generate a Web App project

    - mvn archetype:generate -DgroupId=com.jjtech -DartifactId=JJtechBatchApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false

The above command will generate a standard maven project template for a simple Web Application. Edit folder structure to achieve the desired java structure and add required java source code files. 


## Build WebApp Artifacts 

In the directory with teh pom.xml config file. Build the java Application  using:

    - mvn clean package 

This builds the **.War** java artifact that can be deployed on a web server like [Tomca](https://tomcat.apache.org/download-90.cgi). 


# Install Tomcat on Jenkins Server to Serve Java WebApp. 

Download Tomcat v9.0.98 

    -  wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.98/bin/apache-tomcat-9.0.98.tar.gz

Unzip the downloaded **.tar.gz ** zip file 

    - tar -xvzf apache-tomcat-9.0.98.tar.gz 

Move the extracted  binaries to desired Tomcat location

    -  sudo mv apache-tomcat-9.0.98 /opt/tomcat

Assign ownership of the directory 

    - sudo chown -R $USER:$USER /opt/tomcat

Make the scripts executable:

    - chmod +x /opt/tomcat/bin/*.sh

If Server running Jenkins and already using **port 8080** , edit Tomcat config file and change **connector port** to **8081**. 

    - sudo vi /opt/tomcat/conf/server.xml 

Save and Exit

    - :wq!

Start Tomcat 

    - /opt/tomcat/bin/startup.sh


Access Tomcat on **http://<server-ip>:8081** 


# Access the Simple WebApp

Copy the **.war** file to Tomcat's **webapps** directory 

    - sudo cp target/JJtechBatchApp.war /opt/tomcat/webapps/

Restart Tomcat 

    - /opt/tomcat/bin/shutdown.sh
    - /opt/tomcat/bin/startup.sh

Tomcat will auto unpack the **.war** file into a directory with the same name. 






    