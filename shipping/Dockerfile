# Build stage
FROM maven:3.8.7-openjdk-18-slim AS build

WORKDIR /opt/shipping

COPY pom.xml ./
RUN mvn dependency:resolve

COPY src ./src
RUN mvn clean package -DskipTests

# Run stage
FROM openjdk:18-jdk-slim

EXPOSE 8080
WORKDIR /opt/shipping

ENV CART_ENDPOINT=cart:8080
ENV DB_HOST=mysql

COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar

CMD ["java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar"]
