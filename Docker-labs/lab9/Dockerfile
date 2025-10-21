# Use Java 17 base image (runtime only)
FROM eclipse-temurin:17-jre

# Create work directory
WORKDIR /app

# Copy the built JAR into the container
COPY target/demo-0.0.1-SNAPSHOT.jar app.jar

# Expose port 8080
EXPOSE 8080

# Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]
