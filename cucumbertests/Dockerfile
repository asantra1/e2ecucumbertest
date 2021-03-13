FROM ubuntu:16.04
RUN apt-get update
RUN apt-get update && apt-get install -y \
  default-jre \
  default-jdk \
  maven \
  curl
RUN mvn -version
RUN mkdir -p $HOME/CucumberTests
WORKDIR $HOME/CucumberTests
COPY pom.xml .
RUN mvn dependency:go-offline
COPY src/ src/
RUN mvn package
ENTRYPOINT ["mvn", "test"]

