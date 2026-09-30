# CST8915-Lab2
# CST8915 Lab 2 - 12-Factor App

**Student Name:** Kaveh Kheir Abadi  
**Student ID:** 041297932  
**Course:** CST8915 Full-stack Cloud-native Development  
**Semester:** Fall 2026  

## Implementation Description

Due to the limitations of my Azure Student account, I was able to create only three VMs instead of four. Therefore, I implemented the required services across the following three VMs:

- **product-service-Rust-petstore** — hosts the **Product Service (Rust)**.
- **RabbitMQ-petstore2** — hosts the **RabbitMQ backing service**.
- **store-front-Vue-petstore** — hosts both the **Store Front (Vue.js)** and the **Order Service (Node.js)**.

## Demo Video

YouTube Demo: [Demo Video](https://youtu.be/E1pFfjh6VP8)

## Service Repositories

- [Order Service](https://github.com/kaveh-kheir-abadi/CST8915-Lab2-Order-Service)
- [Product Service](https://github.com/kaveh-kheir-abadi/CST8915-Lab2-Product-Service)
- [Store Front](https://github.com/kaveh-kheir-abadi/CST8915-Lab2-Store-Front)

## Reflection Questions

### 1. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?

For the order-service, I added environment variables for the RabbitMQ connection string and port using a `.env` file. I also added the `dotenv` dependency so the service can load these values. For the product-service, I added an environment variable for the port instead of hard-coding it in the application. RabbitMQ was also configured as an external backing service instead of running with the application.

### 2. Why is it important to use environment variables instead of hard-coding configurations in your application?

Environment variables keep configuration separate from the application code. This makes it easier to change settings such as ports, service URLs, and connection strings without modifying the source code. It also makes the application more portable and easier to run in different environments because the same code can be used with different configurations. It also helps prevent sensitive information, such as RabbitMQ credentials, from being stored directly in the code repository.

### 3. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?

Separate repositories allow each microservice to be developed and updated independently. Changes to one service do not require changes to the other services. This also makes it easier to deploy and scale each service separately based on its own requirements.
