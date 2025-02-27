# Use a Maven image with Java 8 n
FROM maven:3.6.3-openjdk-8 AS builder

# Set working directory
WORKDIR /app

# Copy the entire project
COPY . .

#RUN chmod +x ./mvnw || true

# Build the project without running tests
RUN mvn clean install -DskipTests

# Use a lightweight OpenJDK 8 JRE image for running the app
FROM openjdk:8-jre

# Set working directory
WORKDIR /app

# Copy the built JAR from the builder stage
COPY --from=builder /app/target/users-api-0.0.1-SNAPSHOT.jar users-api.jar

# Run the application
CMD ["java", "-jar", "users-api.jar"]
