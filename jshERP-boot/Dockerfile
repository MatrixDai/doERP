# Stage 1: Build the application
FROM maven:3.8.6-openjdk-8-slim AS build
WORKDIR /app
COPY . /app
RUN mvn clean package

# Stage 2: Run the application
FROM openjdk:8-jdk-alpine
EXPOSE 9999
COPY --from=build /app/target/*.jar app.jar
ENTRYPOINT ["sleep", "15000", "java","-jar","/app.jar"]
