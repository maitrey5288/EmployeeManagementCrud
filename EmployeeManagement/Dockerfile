FROM maven:3.8.5-openjdk-17 as BUILD
COPY . ./app
workdir /app/
RUN mvn clean package -DskipTests


FROM openjdk:17-jdk

COPY --from=build /app/target/EmployeeCrud.jar EmployeeCrud.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","EmployeeCrud.jar"]