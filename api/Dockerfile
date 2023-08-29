FROM maven:3.9.4-ibmjava AS appserver
COPY . .
RUN mvn -B -f pom.xml -s /usr/share/maven/ref/settings-docker.xml dependency:resolve
RUN mvn -B -s /usr/share/maven/ref/settings-docker.xml package -DskipTests

FROM ibmjava:8-jre-alpine
RUN adduser --gecos "" --disabled-password --home /home/gordon gordon
COPY --from=appserver /target/ddev-0.0.1-SNAPSHOT.jar .
ENTRYPOINT ["java", "-jar", "/ddev-0.0.1-SNAPSHOT.jar"]
CMD ["--spring.profiles.active=postgres"]
