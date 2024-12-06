FROM maven:3-eclipse-temurin-8-alpine AS maven

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:8-jre-alpine

WORKDIR /usr/src/app

COPY --from=maven /app/target/java*.jar backend.jar

CMD ["java","-jar","backend.jar"]

EXPOSE 8448

LABEL maintainer="Maxime"