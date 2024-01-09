# Hosting Website on AWS using Docker, Amazon ECR, and Amazon ECS

![image](https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/fa02dc30-d672-43a4-ba99-97cfd2dad14a)

<img width="478" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/0b8ace57-0814-44cb-a22e-d32202e7a9f9">

## Overview

This DevOps project involves hosting a website on AWS using Docker, Amazon Elastic Container Registry (ECR), and Amazon Elastic Container Service (ECS). These technologies are chosen for scalability, ease of deployment, and efficient management of containerized applications.

## Resources

1. **VPC (Virtual Private Cloud)**
   - Explanation: A VPC provides a logically isolated section of the AWS Cloud where you can launch AWS resources. In this project, it helps create a secure and customizable network environment.

2. **Application Load Balancer (ALB)**
   - Explanation: ALB distributes incoming application traffic across multiple targets, ensuring high availability and fault tolerance. It's used to route traffic to containers in this project.

3. **NAT Gateways**
   - Explanation: NAT gateways allow instances in private subnets to connect to the internet, enabling secure communication for resources like containerized applications.

4. **Security Groups**
   - Explanation: Security groups act as virtual firewalls for instances, controlling inbound and outbound traffic. Specific rules are defined to ensure secure communication between different components.

5. **Amazon Elastic Container Registry (ECR)**
   - Explanation: ECR is a fully managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images. It's used to store and manage container images in this project.

6. **Amazon Elastic Container Service (ECS)**
   - Explanation: ECS is a fully managed container orchestration service that makes it easy to run, stop, and manage Docker containers on a cluster. It automates the deployment of containers, ensuring scalability and flexibility.

7. **Certificate Manager**
   - Explanation: Certificate Manager is used for managing SSL/TLS certificates for secure communication. It provides encryption for data in transit, enhancing the security of the hosted website.

8. **Route 53**
   - Explanation: Route 53 is a scalable and highly available domain name system (DNS) web service. It's used for registering and managing domain names, ensuring users can access the website using a human-readable domain name.

## DevOps Tools

1. **Docker**
   - Explanation: Docker is a platform that enables developers to automate the deployment of applications inside lightweight, portable containers. Containers ensure consistency across different environments.

2. **Docker Hub**
   - Explanation: Docker Hub is a cloud-based registry service that allows you to link to code repositories, build your images, and distribute them. It's used to store and share Docker container images.

3. **GIT**
   - Explanation: GIT is a distributed version control system used for tracking changes in the source code during development. It facilitates collaboration among team members and version control.

4. **GitHub**
   - Explanation: GitHub is a web-based hosting service for version control using GIT. It provides a platform for collaboration and code sharing, allowing multiple contributors to work on the project.

5. **Visual Studio Code**
   - Explanation: Visual Studio Code is a source-code editor that provides powerful editing and debugging capabilities. It's used as the integrated development environment (IDE) for working with Dockerfiles and project configurations.

6. **PowerShell**
   - Explanation: PowerShell is a task automation framework that consists of a command-line shell and scripting language. It's used for executing commands and scripts during the project setup.

## Steps

1. **Create Keypair on Mac**
   - Explanation: Generating a key pair provides secure SSH access to instances and services. This step ensures secure communication during various processes.
   ```bash
   ssh-keygen -t rsa
   ```

2. **Add Public SSH Key to GitHub**
   - Explanation: Adding the SSH key to GitHub allows secure authentication, enabling interaction between the local development environment and the GitHub repository.
   ```bash
   cat .ssh/id_rsa.pub
   ```
   <img width="221" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/f924a54c-babb-414b-8d9a-899444b5c139">

3. **Install Git**
   - Explanation: Git is installed to enable version control for the project. It tracks changes in code, allowing collaboration and maintaining a history of modifications.
   ```bash
   git --version
   ```
   <img width="239" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/475bc59e-3f6d-41b8-acc8-d9b9478e8d1b">

4. **Install Visual Studio Code**
   - Explanation: Visual Studio Code is chosen as the IDE for its features that enhance code development, making it easier to manage project files.
   ```bash
   # Installation steps specific to your platform
   ```

5. **Clone Dockerfile Repository**
   - Explanation: Cloning the Dockerfile repository provides a local copy of project files. It facilitates version control, collaboration, and access to project resources.
   ```bash
   git clone git@github.com:bconway1906/docker-projects.git
   ```
   <img width="272" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/43ab420e-e762-46fe-a1aa-de3a9adab145">

6. **Enable Virtualization (For Windows)**
   - Explanation: Virtualization is required for running Docker on Windows. This step ensures compatibility with Docker containers.

7. **Download and Install Docker**
   - Explanation: Installing Docker provides the necessary platform for containerizing applications. Docker is essential for creating, deploying, and managing containerized services.
   ```bash
   docker -v
   ```

8. **Create Dockerfile**
   - Explanation: A Dockerfile contains instructions for building a Docker container image. It specifies the base image, application configuration, and dependencies needed for the containerized application.
   ```bash
   # Create Dockerfile using Visual Studio Code
   ```
   <img width="335" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/c0e460a6-bbef-452e-b6c7-e2f2356ca31e">


9. **Build and Test the Container**
   - Explanation: Building and testing the container image locally ensures that it functions as expected before pushing it to repositories. This step verifies the correctness of the Dockerfile.
   ```bash
   docker build -t Jupiter .
   ```
   <img width="295" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/25370a4b-35ad-493d-bb0d-f065a97154fe">

   <img width="259" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/0a3d4e3d-2038-42fc-ac61-2a85c09f4a30">

   <img width="347" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/7ab0109b-0153-4c23-91e9-dbc21e5197ba">

10. **Push Image to Docker Hub**
    - Explanation: Pushing the Docker image to Docker Hub makes it accessible to other developers and deployment processes. Docker Hub serves as a centralized repository for sharing container images.
    ```bash
    docker push bconway1906/Jupiter
    ```
    <img width="337" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/7f5aaec8-2a9d-42a3-8167-37bb23d35b7a">

    <img width="468" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/ea8184fa-5aee-421f-898a-0402a5371f7a">

    <img width="468" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/c0a5e550-932d-4152-80e1-d7e2906f8345">

11. **Download AWS CLI**
    - Explanation: AWS CLI is installed to interact with AWS services through the command line. It enables automation and management of AWS resources.
    ```bash
    aws --version
    ```

12. **Create IAM User for ECR**
    - Explanation:

 Creating an IAM user with administrator access allows programmatic access to AWS services. This user is used for authentication when interacting with Amazon ECR.
    ```bash
    # Console steps: Attach policies, create access key
    ```

13. **Create Access Key for IAM User**
    - Explanation: Creating an access key provides secure authentication for the IAM user when interacting with AWS services programmatically.
    ```bash
    # Console steps
    ```
    
14. **Configure AWS CLI**
    - Explanation: Configuring the AWS CLI with access keys enables secure communication between the local environment and AWS services.
    ```bash
    aws configure
    ```

15. **Create Amazon ECR Repository**
    - Explanation: Creating an ECR repository provides a centralized location for storing Docker container images. It's a secure and scalable solution for managing container images.
    ```bash
    aws ecr create-repository --repository-name jupiter --region us-east-1
    ```

16. **Push Image to ECR Repository**
    <img width="347" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/cacbfb23-fccf-4422-8a0e-20863cb34320">

     - Explanation: Tagging and pushing the Docker image to ECR ensures that it's available for deployment using Amazon ECS. ECR serves as a reliable registry for container images.
    ```bash
    # Tag the image
    docker tag jupiter 629978445734.dkr.ecr.us-east-1.amazonaws.com/jupiter
    
    # Authenticate Docker to the registry
    aws ecr get-login-password | docker login --username AWS --password-stdin 629978445734.dkr.ecr.us-east-1.amazonaws.com
    
    # Push the image to ECR
    docker push 629978445734.dkr.ecr.us-east-1.amazonaws.com/jupiter
    ```
    <img width="353" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/0555702e-e202-42b1-b124-ba1d03be2741">
    
18. **Build Three-Tier AWS Network using CloudFormation**
    <img width="334" alt="image" src="https://github.com/bconway1906/Host-Website-on-AWS-using-CloudFormation-Docker-Amazon-ECR-and-Amazon-ECS/assets/148906255/051e586f-1df4-4485-be09-a5258da5f17c">
    - Explanation: CloudFormation is used to automate the creation of AWS resources, ensuring consistency and reproducibility. The three-tier network architecture is designed for scalability and reliability.
    ```bash
    # Run CloudFormation template
    ```

20. **Create Security Groups**
    - Explanation: Security groups are created to define inbound and outbound rules for network traffic. This step ensures secure communication between different components of the architecture.
    ```bash
    # Console steps
    ```

21. **Create Application Load Balancer (ALB)**
    - Explanation: ALB is provisioned to distribute incoming application traffic among ECS containers. It enhances availability and fault tolerance.
    ```bash
    # Console steps
    ```

22. **Create ECS Cluster using AWS Fargate**
    - Explanation: AWS Fargate is chosen for ECS cluster management as it provides serverless container execution. This eliminates the need to manage infrastructure, enhancing scalability.
    ```bash
    # Console steps
    ```

23. **Create Task Definitions in Amazon ECS**
    - Explanation: Task definitions define parameters for running Docker containers in ECS. It includes container configurations, environment variables, and other settings.
    ```bash
    # Console steps
    ```

...

## Clean Up

Follow these steps to clean up resources created during the project:

1. **Delete ECS Cluster**
2. **Delete Tasks**
3. **Delete ALB**
4. **Delete Target Groups**
5. **Delete Security Groups (Container Group and ALB)**
6. **Delete NAT Gateway (under VPC dashboard)**
7. **Delete CloudWatch Log Groups**

---
