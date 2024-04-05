# Deployment Guide for AWS ECS Docker

Follow these steps to deploy the microservices on AWS ECS using Docker:

## Step 1: Create Private Repository on ECR

1. **Create Repositories**: Create a private repository on Amazon Elastic Container Registry (ECR) for each microservice with default settings.
   - **Product**
   - **User**
   - **Order**
   - **Payment**

## Step 2: Create Task Definition

1. **Define Tasks**: Create a task definition for each microservice with type "Fargate".
2. **Configure Roles**: Configure task roles with necessary access permissions, including access to the corresponding ECR repositories.
3. **Set Image URI**: Set container name and repository ARN (from Step 1) in image URI.
4. **Specify Ports**: Specify container ports and add CloudWatch for logging.

## Step 3: Create ECS Cluster

1. **Create Cluster**: Create a new Amazon ECS cluster with type "Fargate".
2. **Cluster Setup**: Ensure all microservices, tasks, and services belong to this cluster.

## Step 4: Create Service

1. **Service Creation**: Create a separate service for each microservice within the cluster.
2. **Configuration**: Name the service, select the corresponding task definition, and choose Fargate with the latest platform version.
3. **Desired Task Count**: Set the desired task count to 2 for redundancy.
4. **Network Setup**: Configure VPC, security groups, and ensure port access to any IP.
5. **Load Balancer Setup**: Set up an Application Load Balancer (ALB) at the same port, create separate target groups for each microservice at different ports, and add health check paths.

## Repository Configuration

1. **Branch Check**: Ensure you are on the `ecs-docker` branch.
2. **Dockerfile**: Create a Dockerfile in the root directory.

```Dockerfile
FROM node:17.9.1
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .
EXPOSE 4040
CMD ["npm", "run", "server"]
```

3. **Task Definition File**: Copy the JSON content from the AWS task definition and create a file in your base directory (e.g., ecom-user-td.json).
4. **GitHub Workflows**: Create a directory .github/workflows and a file cicd-workflows.yml.
        Refer to the file shared in the microservice repositories at the ecs-docker branch.
        Modify the file with your AWS access key, secret access key, repository name, task definition name, container name, service name, and cluster name.
5. **Commit Changes**: Commit any changes to the ecs-docker branch, and GitHub Actions will automatically create and push Docker images to AWS ECS Docker.
6. **Monitoring**: Monitor the deployment progress in GitHub Actions.

Follow these steps to deploy the microservices on AWS ECS using Docker. Ensure to replace placeholder values with actual AWS resources and credentials.
