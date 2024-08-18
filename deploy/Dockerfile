FROM maven:3.8.5-openjdk-17 AS build
COPY ..
RUN mvn clean package -DskipTests
FROM openjdk:17.0.1-jdk-slim
COPY --from=build /target/deploy-0.0.1.jar app_deploy.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app_deploy.jar"]