# Use Maven base image with Java 17
FROM maven:3.9.5-eclipse-temurin-17 AS build

# Create app directory
WORKDIR /app

# Copy the application source code into the container
COPY . .

# Build the app (this will generate the jar in target/)
RUN mvn clean package -DskipTests

# -------------------------------
# Create a new lightweight image for running the app
FROM eclipse-temurin:17-jdk

WORKDIR /app

# Copy only the built jar from the previous stage
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.jar app.jar

# Expose port 8080
EXPOSE 8080

# Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]
