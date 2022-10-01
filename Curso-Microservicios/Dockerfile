FROM maven:3.8.5-jdk-11 as builder
WORKDIR /workspace/app
COPY . .
RUN ["mvn", "clean", "package"]

FROM --platform=linux/arm64/v8 amazoncorretto:8
COPY --from=builder /workspace/app/microservicio-web/target/microservicio-web-1.0-SNAPSHOT.jar app.jar
CMD ["java", "-jar", "app.jar"]
