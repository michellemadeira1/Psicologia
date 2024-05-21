# Etapa de construção
FROM maven:3.8.5-openjdk-11 as build
WORKDIR /app
COPY . /app
RUN mvn clean package -X -DskipTests

# Etapa de execução
FROM openjdk:11.0.1-jdk-slim
WORKDIR /app
COPY --from=build /app/target/*.jar /app/springdeskintegrador.jar
ENTRYPOINT ["java", "-jar", "/app/springdeskintegrador.jar"]
