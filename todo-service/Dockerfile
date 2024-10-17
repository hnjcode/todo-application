# Use an official OpenJDK 8 runtime as a parent image
FROM openjdk:8-jdk-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy the built jar file from the host machine to the container
COPY ./target/todo-service-0.0.1-SNAPSHOT.jar /app/todo-service.jar

# Expose the application port
EXPOSE 8080

# Run the jar file
CMD ["java", "-jar", "/app/todo-service.jar"]