# Build stage
FROM maven:3.9-eclipse-temurin-17 AS builder

# Set working directory
WORKDIR /app

# Copy Maven configuration
COPY pom.xml .

# Download dependencies
RUN mvn dependency:go-offline

# Copy source code
COPY src ./src

# Build application
RUN mvn clean package -DskipTests

# Final stage
FROM eclipse-temurin:17-jre

# Set working directory
WORKDIR /app

# Copy generated JAR
COPY --from=builder /app/target/*.jar app.jar

# Expose application port
EXPOSE 5002

# Start Spring Boot application
CMD ["java", "-jar", "app.jar"]