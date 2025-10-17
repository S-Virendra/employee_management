# Base image
FROM eclipse-temurin:17-jdk-alpine

# Set working directory
WORKDIR /app

# Copy pom.xml and download dependencies
COPY pom.xml .
RUN ./mvnw dependency:go-offline || mvn dependency:go-offline

# Copy source code
COPY src ./src

# Package the app
RUN ./mvnw package || mvn package

# Expose port
EXPOSE 8080

# Run the jar
CMD ["java", "-jar", "target/employeeapi-0.0.1-SNAPSHOT.jar"]
