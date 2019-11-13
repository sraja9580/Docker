FROM openjdk:8-jdk-alpine	
#ADD target/hello-world-rest-api.jar hello-world-rest-api.jar
#ENTRYPOINT ["sh", "-c", "java -jar /hello-world-rest-api.jar"]
#TO MAKE DOCKE FILE REUSABLE
ADD target/*.jar app.jar
ENTRYPOINT ["sh", "-c", "java -jar /app.jar"]
#TO MAKE DOCKE FILE REUSABLE END