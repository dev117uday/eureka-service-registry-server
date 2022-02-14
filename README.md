# Service Registry Eureka Server

- Create directories

```bash
mkdir src/main/resources
touch src/main/resources/application.yml
touch src/main/resources/application.properties
```

- Create `application.yml`

```yml
server:
  port: 8761

eureka:
  client:
    fetchRegistry: 'false'
    registerWithEureka: 'false'
```

- or Create `application.properties`

```properties
server:
  port: 8761

eureka:
  client:
    fetchRegistry: 'false'
    registerWithEureka: 'false'
```

- Build and run with Docker

```bash
"./mvnw" package -f "pom.xml"
docker build -f Dockerfile -t my-eureka-server .
docker run -d --name eureka -p 8761:8761 my-eureka-server
```