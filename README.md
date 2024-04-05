# Ecommerce Microservices Project

Welcome to the Ecommerce Microservices project! This repository serves as the central hub for our microservices-based system that manages a simple e-commerce application. Emphasis has been placed on implementing concurrency control and ensuring the system can handle clustering for high availability.

## Table of Contents

- [Introduction](#introduction)
- [Microservices Architecture](#microservices-architecture)
- [Concurrency Control](#concurrency-control)
- [Clustering and High Availability](#clustering-and-high-availability)
- [Database Integration](#database-integration)
- [APIs and Communication](#apis-and-communication)
- [Authentication and Authorization](#authentication-and-authorization)
- [Features](#features)
- [Bonus Features](#bonus-features)
- [Getting Started](#getting-started)

## Introduction

In this project, we have built a microservices-based system for managing a simple e-commerce application. The system handles user authentication, product management, and order processing. Our goal is to ensure scalability, maintainability, and high availability of the system.

## Microservices Architecture

Our system is structured into the following microservices:

- **User Authentication Service**: Manages user authentication and authorization.
- **Product Management Service**: Handles product catalog management.
- **Order Processing Service**: Processes orders placed by users.
- **Payment Service**: Facilitates secure payment processing for orders.

## Concurrency Control

To ensure data integrity, especially in the product management service, we have implemented concurrency control mechanisms. One such mechanism is the optimistic locking feature provided by Mongoose.

## Clustering and High Availability

To ensure high availability, we have set up clustering mechanisms for our microservices on AWS ECS Docker, allowing deployment on multiple nodes or containers. The system remains available even if one node/container goes down. Each of the four microservices is deployed with a minimum of two tasks, which share the load using a common load balancer to ensure smooth functioning and fault tolerance.

## Database Integration

Our system is integrated with a MongoDB database to store various types of data including user information, product details, and order history. The database schema is carefully designed to efficiently handle these entities, ensuring optimal performance. Additionally, our microservices are equipped with appropriate queries to interact with the database seamlessly.

## APIs and Communication

We have developed RESTful APIs for each microservice, facilitating smooth communication between them. 
These APIs cover a wide range of functionalities including user registration, CRUD operations for products, order management, and payment processing. Microservices interact with each other through these REST APIs, allowing both synchronous and asynchronous calls as required. This ensures seamless integration and coordination between different components of our system.

## Authentication and Authorization

We've implemented user authentication and authorization using JWT Tokens and cookies to secure access to protected endpoints. This ensures that users must authenticate themselves with valid credentials before accessing sensitive resources. 
Access is restricted so that users can only interact with their own orders and authorized product data, enhancing overall system security.


## Features

- **Code Quality**: Our codebase follows best practices, is clean, well-documented, and maintainable.
- **Scalable Architecture**: Built on microservices architecture, allowing seamless scalability and flexibility.
- **Modular Design**: Each microservice is independent, enabling easy maintenance and updates.
- **Secure Transactions**: Payment processing ensures the highest level of security for users' financial transactions.
- **Version Control**: We used Git to track changes in our code. Links to individual microservice repositories:
  - [User Microservice Repository](https://github.com/PriyanshuGarg15/ecom-user)
  - [Product Microservice Repository](https://github.com/PriyanshuGarg15/ecom-product)
  - [Order Microservice Repository](https://github.com/PriyanshuGarg15/ecom-orders)
  - [Payment Microservice Repository](https://github.com/PriyanshuGarg15/ecom-payment)
- **Error Handling**: Comprehensive error handling and logging are implemented across our microservices.
- **Testing**: We have written unit tests for critical components, including concurrency control mechanisms (refer User Microservice).
- **Deployment**: Clear instructions for deploying and running our microservices are provided in the [Deployment Guide](deployment.md).

## Bonus Features
- **API Rate Limiting**: Implemented to prevent abuse.
- **Monitoring and Alerting**:  We employ AWS CloudWatch for comprehensive monitoring and alerting, ensuring the stability and operational efficiency of our services at the AWS Task level.

## Submission

- [Main Repository](https://github.com/PriyanshuGarg15/ECOM-MICROSERVICES/)
- [Deployment Guide](deployment.md)

## Getting Started

To get started with our Ecommerce Microservices project, follow these steps:

1. **Clone the Repository**: Clone the repository of microservice to your local machine using `git clone /* repo url */`
  - [User Microservice Repository](https://github.com/PriyanshuGarg15/ecom-user)
  - [Product Microservice Repository](https://github.com/PriyanshuGarg15/ecom-product)
  - [Order Microservice Repository](https://github.com/PriyanshuGarg15/ecom-orders)
  - [Payment Microservice Repository](https://github.com/PriyanshuGarg15/ecom-payment)
2. **Set Up Microservices**: Navigate to each microservice repository and follow the setup instructions provided in their respective README files.
3. **Set Up Microservice on AWS ECS DOCKER**: Navigate to [Deployment Guide](deployment.md).
4. **Run the Project**: Start each microservice locally and ensure they are running correctly.
5. **Explore and Contribute**: Dive into the codebase, explore the functionalities, and consider contributing to the project!

