# ECS Fargate Blue/Green Deployment with CodePipeline

This repository demonstrates a complete CI/CD pipeline using **AWS CodePipeline**, **CodeBuild**, and **Amazon ECS Fargate** with **blue/green deployment strategy**.

## Architecture Overview

- **Source**: GitHub repository (this repo)
- **Build**: AWS CodeBuild (buildspec.yml)
- **Deploy**: ECS Fargate with blue/green using CodeDeploy
- **Load Balancer**: Application Load Balancer (ALB)

## Folder Structure

├── app/ # Sample web application code (e.g., index.html)

├── Dockerfile # Docker build file for app

├── buildspec.yml # CodeBuild instructions

├── taskdef.json # ECS Task Definition

├── appspec.yaml # CodeDeploy AppSpec for ECS blue/green


## Prerequisites

- AWS CLI configured
- ECS Cluster and Fargate service setup
- ALB with listener rules for blue/green
- ECR repository created and attached
- IAM roles for CodePipeline, CodeBuild, and ECS tasks
- S3 bucket for artifacts

## How to Use

1. **Push code to main branch**
2. **Pipeline triggers automatically**
3. **Build image, push to ECR**
4. **Deploys new task definition with blue/green deployment**
5. **Monitor deployment in CodeDeploy console**

## Test

Once deployed, access the application via the ALB DNS:

--bash

curl http://<your-alb-dns>

