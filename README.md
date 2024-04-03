# API Project Introduction

This project is aimed at developing a RESTful API using Flask, Docker, and integrating it with AWS services such as Amazon ECR and Amazon EC2. The API provides functionality for user registration, text similarity detection, and token management.

## Features

- User registration: Allows users to register with a unique username and password, storing their credentials securely in a MongoDB database.
- Text similarity detection: Calculates the similarity score between two text inputs using spaCy's natural language processing capabilities.
- Token management: Implements token-based authentication and authorization, allowing users to consume API services based on their token balance.

## Technologies Used

- Flask: A lightweight Python web framework for building web applications and APIs.
- Docker: A containerization platform used to package the application and its dependencies into containers for consistent deployment across different environments.
- Amazon ECR (Elastic Container Registry): A fully managed Docker container registry provided by AWS, used to store, manage, and deploy Docker container images.
- Amazon EC2 (Elastic Compute Cloud): A scalable virtual cloud server provided by AWS, used to deploy and run Docker containers in production.

## Continuous Integration/Continuous Deployment (CI/CD)

The project employs a CI/CD pipeline to automate the deployment process, ensuring rapid and reliable delivery of changes to production. The pipeline includes the following stages:

1. **Code Commit**: Developers push code changes to a version control system like Git, which triggers the CI/CD pipeline.
2. **Code Build**: The CI system builds the Docker image, runs tests, and packages the application.
3. **Container Registry**: The Docker image is pushed to Amazon ECR, where it is stored securely.
4. **Infrastructure Provisioning**: Using infrastructure-as-code tools like AWS CloudFormation or Terraform, the required AWS resources (e.g., EC2 instance) are provisioned.
5. **Deployment**: The Docker image is pulled from Amazon ECR and deployed to the EC2 instance, making the updated version of the API available.

## Project Structure

- `app.py`: Main Flask application file containing route definitions and business logic.
- `Dockerfile`: Docker configuration file defining the environment and dependencies for running the Flask application.
- `requirements.txt`: File listing the Python dependencies required by the Flask application.
- `.gitlab-ci.yml` (or equivalent): CI/CD pipeline configuration file defining the stages and steps for building, testing, and deploying the application.

## Usage

To run the API locally for development purposes, follow these steps:

1. Clone the repository to your local machine.
2. Install Docker and Docker Compose if not already installed.
3. Navigate to the project directory and run `docker-compose up` to build and start the containers.
4. Access the API endpoints using `http://localhost:<port>` in your web browser or API testing tool (e.g., Postman).

For production deployment on AWS, configure the CI/CD pipeline to automate the build, test, and deployment process. Use Amazon ECR to store Docker images and Amazon EC2 to run the containers in a scalable and reliable manner.
