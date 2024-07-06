# Beginner SRE Projects

## 1. Foundation: Python and AWS
**Project: AWS Resource Monitor**

### Setup:
- [ ] Set up an AWS Free Tier account and enable MFA
- [ ] Install and configure the AWS CLI on your local machine
- [ ] Create a sandbox environment:
  - [ ] Use AWS CloudFormation to create a VPC with one public and one private subnet
  - [ ] Set up necessary security groups

### Tasks:
- [ ] Launch EC2 instances for testing:
  - [ ] Create 2 t2.micro EC2 instances in your sandbox VPC (1 public, 1 private)
  - [ ] Tag instances (e.g., "Environment: Sandbox", "Purpose: Testing")
- [ ] Write a Python script using boto3 to:
  - [ ] List all EC2 instances in your account
  - [ ] Filter instances based on tags
  - [ ] Start and stop EC2 instances based on their tags
- [ ] Implement S3 operations:
  - [ ] Write a Python script to create an S3 bucket
  - [ ] Extend the script to upload a file to the bucket
  - [ ] Add functionality to list bucket contents and delete objects
- [ ] Error handling and logging:
  - [ ] Implement comprehensive error handling in both scripts
  - [ ] Add logging to track script operations and errors
- [ ] Create a CLI:
  - [ ] Develop a command-line interface that combines EC2 and S3 functionality
  - [ ] Include help documentation for each command
- [ ] Testing:
  - [ ] Thoroughly test all functions with your sandbox resources
  - [ ] Document any issues encountered and how you resolved them
- [ ] Clean up:
  - [ ] Delete the S3 bucket and its contents
  - [ ] Terminate the EC2 instances
  - [ ] Delete the CloudFormation stack to remove the VPC

## 2. Infrastructure as Code with Terraform
**Project: Multi-tier Web Application Infrastructure**

### Setup:
- [ ] Install Terraform on your local machine
- [ ] Set up a new directory for your Terraform project
- [ ] Configure AWS credentials for Terraform use

### Tasks:
- [ ] VPC Module:
  - [ ] Create a Terraform module for a VPC with 1 public and 1 private subnet
  - [ ] Include necessary route tables and an Internet Gateway
- [ ] EC2 Module:
  - [ ] Create a module for EC2 instances with security groups
  - [ ] Use t2.micro instances to stay within free tier limits
- [ ] RDS Module:
  - [ ] Create a module for an RDS database (use the free tier eligible option)
- [ ] S3 and DynamoDB for State Management:
  - [ ] Set up an S3 bucket for remote state storage
  - [ ] Create a DynamoDB table for state locking
- [ ] Main Configuration:
  - [ ] Create a main.tf file that uses all your modules to set up a basic three-tier architecture
  - [ ] Use variables for customizable inputs (e.g., instance types, DB settings)
- [ ] Implement a simple web application:
  - [ ] Deploy a basic web server on the EC2 instance
  - [ ] Configure the web server to connect to the RDS database
- [ ] CI/CD Pipeline:
  - [ ] Set up a GitHub repository for your Terraform code
  - [ ] Create a GitHub Actions workflow to:
    - [ ] Validate Terraform configurations
    - [ ] Plan Terraform changes
    - [ ] Apply changes (with manual approval for production)
- [ ] Testing:
  - [ ] Apply your Terraform configuration to create the infrastructure
  - [ ] Verify that all components are working as expected
  - [ ] Test the web application to ensure it can connect to the database
- [ ] Documentation:
  - [ ] Write clear documentation for your modules and main configuration
  - [ ] Include instructions for using your CI/CD pipeline
- [ ] Clean up:
  - [ ] Use Terraform to destroy all created resources
  - [ ] Confirm that all AWS resources have been properly removed

## 3. Containerization with Docker
**Project: Containerized Microservices Application**

### Setup:
- [ ] Install Docker on your local machine
- [ ] Set up a GitHub repository for your project

### Tasks:
- [ ] Create a simple microservices application:
  - [ ] Develop a basic frontend service (e.g., using React or Vue.js)
  - [ ] Create an API service (e.g., using Express.js or Flask)
  - [ ] Set up a database service (e.g., MongoDB or PostgreSQL)
- [ ] Dockerize each service:
  - [ ] Write Dockerfiles for each service
  - [ ] Build Docker images for each service
- [ ] Implement Docker Compose:
  - [ ] Create a docker-compose.yml file to define and run the multi-container application
  - [ ] Include environment variables and volume mounts as needed
- [ ] Set up a reverse proxy:
  - [ ] Add Nginx as a reverse proxy in your Docker Compose setup
  - [ ] Configure Nginx to route requests to the appropriate services
- [ ] Implement a CI/CD pipeline:
  - [ ] Create a GitHub Actions workflow to:
    - [ ] Build Docker images
    - [ ] Run tests
    - [ ] Push images to Docker Hub (or AWS ECR)
- [ ] Local testing:
  - [ ] Run the application locally using Docker Compose
  - [ ] Verify that all services are communicating correctly
- [ ] Documentation:
  - [ ] Write a README with instructions for running the application locally
  - [ ] Document the CI/CD process and how to deploy changes
- [ ] Clean up:
  - [ ] Ensure all containers and volumes are removed after testing
  - [ ] Remove any unused Docker images to free up space