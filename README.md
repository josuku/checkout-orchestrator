# NestJS Checkout API

Basic checkout implementation using microservices and Docker

Requirements:
- Node Package Manager
- Docker with Docker-Compose

Implemented in NestJS and Angular to use the same language in front and back

## Running the app

Install Docker Desktop if you do not have it. Run the following command on a terminal to start-up the system:
```bash
$ docker-compose up
```

## Solution Description

The solution is partitioned in several projects:

- checkout-orchestrator: Contains the docker-compose.yml file to orchestrate the solution in Docker. Next projects are added as submodules.

- co-client: Basic client in Angular to send and receive data to and from the microservices, using the public API.

- co-checkout-service: microservice implemented in NestJS. It exposes a public API, and can communicate with other microservices to achieve the checkout process.

- co-bill-service: microservice implemented in NestJS as microservice, which uses the request-response message style to exchange messages with other microservices. It process the sum of all products in a order.

- co-logistic-service: microservice implemented in NestJS as microservice. It also uses the request-response message style. It creates a sent order.

- co-order-service: hybrid application with microservive and API, build in NestJS. Order management

## Exposed Services

- co-client can be accesed on: http://localhost:80

- co-checkout-service API is exposed in http://localhost:3001/api/v1

- co-bill-service NestJS microservice uses port 3002

- co-logistic-service NestJS microservice uses port 3003

- co-order-service NestJS microservice uses port 3004 and API service uses port 3005

## Third party services

Application uses MySql container with PhpMyAdmin container to store and access the info
