FROM containers-environment AS builder
WORKDIR /containers
COPY . .
RUN mvn clean package

FROM openjdk:11-jdk
WORKDIR /containers
COPY --from=builder /containers/target/containers-1.0.jar ./containers.jar
CMD java -jar containers.jar
