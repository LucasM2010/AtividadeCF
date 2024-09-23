
FROM maven:3.9.0-eclipse-temurin-17 AS build


WORKDIR /app


COPY pom.xml .


COPY src ./src


RUN mvn dependency:go-offline


RUN mvn clean package


FROM eclipse-temurin:17-jdk


WORKDIR /app


COPY --from=build /app/target/convertion-0.0.1-SNAPSHOT.jar app.jar


EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]

