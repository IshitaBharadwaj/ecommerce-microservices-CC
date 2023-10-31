# E-Commerce Microservices with Spring Boot 

Implementation of an E-Commerce system with Spring Boot and Cloud using RESTful microservices, organized into multiple modules to enhance scalability and maintainability. <br/>
A team project as part of UE20CS351 - Cloud Computing Course at PES University.

### 🔨Technologies Used <br/> 
- Spring Boot <br/>
- Postman <br/>
- Maven
- Docker <br/>
- Kubernetes <br/>
- Jenkins <br/>
- MongoDB <br/>
- MySQL/PostgreSQL <br/>


<br/>

### Architecture
![Diagram](./report/architecture-diagram.png "Arch Diagram")

### 🛒 Services <br/>
>[`order-service`](./order-service/) <br/>
[`inventory-service`](./inventory-service) <br/>
[`product-service`](./product-service/) <br/>
[`notification-service`](./notification-service/) <br/>

<br/>

### ⛓️ Infrastructure 

>[`api-gateway`](./api-gateway/) <br/>
[`discovery eureka server`](./discovery-server/) <br/>
[`prometheus`](./prometheus/) <br/>
[`grafana`](./grafana/) <br/>
[`prometheus`](./prometheus/) <br/>
`mongo` <br/>
`postgres/mysql` <br/>
`zipkin` <br/>
`zookeeper` <br/>
`keycloak` <br/>

<br/>

### Run the application using Docker

1. Run `mvn clean package -DskipTests` to build the applications and create the docker image locally.
2. Run `docker-compose up -d` to start the applications.

### Run the application without Docker

1. Run `mvn clean verify -DskipTests` by going inside each folder to build the applications.
2. Run `mvn spring-boot:run` in each folder to start the applications.

**☸️ Kubernetes deployment in [k8s](./k8s/)<br/>**
 **🐳 Images at [Docker Hub](https://hub.docker.com/u/hitajuneja)**
