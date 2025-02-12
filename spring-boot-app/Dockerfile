# Build step
FROM maven:3.8.5-openjdk-17 AS builder
WORKDIR /app
RUN git clone https://github.com/kkenan/basic-microservices.git .
RUN mvn package 

# Runtime step
FROM eclipse-temurin:17-jdk-alpine
COPY --from=builder /app/spring-boot-app/target/spring-boot-app-0.0.1-SNAPSHOT.jar /app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]