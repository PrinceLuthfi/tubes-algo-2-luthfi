# Tahap 1: Build aplikasi menggunakan Maven dan JDK 17
FROM maven:3.9-eclipse-temurin-17 AS build
COPY . .
RUN mvn clean package -DskipTests

# Tahap 2: Jalankan aplikasi menggunakan JDK yang lebih ringan
FROM eclipse-temurin:17-jre-jammy
COPY --from=build /target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app.jar"]
