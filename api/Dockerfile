FROM maven:3.8.4-jdk-8 AS build
COPY srs-api /usr/src/srs-api
COPY pom.xml /app
WORKDIR /app
RUN mvn clean install
FROM openjdk:8-jdk-alpine
COPY --from=stage /app/target/srs-api-0.0.1-SNAPSHOT.jar /app/srs-api-0.0.1-SNAPSHOT.jar/app/app.jar
WORKDIR /app
EXPOSE 8080
CMD ["java", "-jar", "app,jar"]
