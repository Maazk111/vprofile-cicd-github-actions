# Stage 1: Build Stage
FROM maven:3.9.6-eclipse-temurin-17 AS build-image

# Copy everything from current directory into /app inside container
COPY . /app
WORKDIR /app

# Build the artifact using Maven
RUN mvn install

# Stage 2: Runtime Stage
FROM tomcat:10.1.15-jdk17
COPY --from=build-image /app/target/vprofile-v2.war /usr/local/tomcat/webapps/
