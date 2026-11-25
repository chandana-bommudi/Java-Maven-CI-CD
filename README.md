# Java Maven CI/CD Project

## Project Overview
Built and deployed a Java web application using Jenkins, Maven, AWS EC2 and Apache Tomcat.

## Technologies Used
- AWS EC2
- Ubuntu Linux
- Jenkins
- Java 21
- Maven
- Apache Tomcat 10
- Git and GitHub

## CI/CD Workflow
1. Source code is maintained in GitHub.
2. Jenkins executes the pipeline.
3. Maven builds the Java application.
4. Maven generates a WAR file.
5. Jenkins transfers the WAR file to the Tomcat server using SSH/SCP.
6. Tomcat deploys the application.
7. Jenkins verifies deployment using curl.

## Deployment URL
http://<Tomcat-Public-IP>:8080/myapp/

## Project Result
Successfully automated the build and deployment of a Java web application using Jenkins and Tomcat hosted on AWS EC2.
