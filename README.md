### Description

The QuotesDevOpsProject showcases the complete workflow for deploying an application using modern DevOps practices. It features a Quote Management System built entirely with Python for both the backend and frontend and an AWS RDS MySQL database. The project is organized into repositories for applications, infrastructure, and GitOps, and includes a fully automated CI/CD pipeline for streamlined deployments.

This project highlights the creation of a reliable and automated development environment, ensuring that changes are tested and deployed efficiently while maintaining consistency throughout the process.

## Project Structure
The project is organized into the following main directories:

1. **Application Repository**:
   - Hosts the application code for both the frontend and backend.
   - Contains a Helm chart for Kubernetes deployments.
   - Includes a CI/CD pipeline file located in the `.github/workflows` directory:
     - Builds Docker images.
     - Pushes images to **AWS ECR**.
     - Updates the image tag in the GitOps repository.
   - The application directory also includes a `docker-compose` file for running the application locally.

2. **Infrastructure Infrastructure**:
   - Utilizes **Terraform** for Infrastructure as Code (IaC).
   - The modules directory contains a 2 main modules named eks-infra and eks-helm: 
     - eks-infra provisions infrastructure, including **EKS**, **VPC**, **RDS**, and other AWS components.
     - eks-helm provisions **helm charts**, **OpenID connect provider** for the cluster, etc.
   - environment directory includes a `main.tf` file for each environment:
     - Executes the platform module with environment-specific configurations.
      
3. **GitOps Repository**:
   - App-chart directory contains the helm chart for the quotes application.
   - Environments directory includes helm charts with environment spcific values files.
   - Templates directory for managing application templates. 
   - Seeds directory to monitor values files changes (e.g., image tags) and automatically trigger **ArgoCD** for deployment updates.
