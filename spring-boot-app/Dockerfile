# Build step
FROM maven:3.9.9-amazoncorretto-8-alpine AS builder
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/kkenan/basic-microservices.git .
RUN mvn -f spring-boot-app/pom.xml clean package

# Runtime step
FROM amazoncorretto:8-alpine-jre
COPY --from=builder /app/spring-boot-app/target/spring-boot-app-*.jar /app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
