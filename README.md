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

---

## Features

### Full-Stack Employee Management System
- **Backend**: Python.
- **Frontend**: Python.
- **Database**: AWS RDS MySQL.

### CI/CD Pipeline
- Fully automated build, test, and deployment processes managed with GitHub Actions and ArgoCD.
- Docker images are built and pushed to AWS ECR.
- Helm charts are updated with the latest image tags in the GitOps repository for seamless deployments.

### Infrastructure as Code (IaC)
- Terraform is used to manage AWS infrastructure with a modular setup.
- Provisions resources such as EKS clusters, VPC, RDS, and other required components.

### Monitoring and Logging
- **Prometheus** and **Grafana** for monitoring:
  - Prometheus collects and stores metrics.
  - Grafana provides real-time dashboards for visualizing metrics.

### External Secrets Integration
- **External Secrets** are used to securely manage sensitive information such as database credentials.
- Deployed using the **External Secret** Helm chart via Terraform.
- Works seamlessly with `ClusterStore` and `ExternalSecret` resources in the application Helm chart.
- Retrieves credentials securely from **AWS Secrets Manager**.

### GitOps with ArgoCD
- Automates Kubernetes deployments by detecting updates in the values file and applying changes.
- Ensures consistency and efficiency in deployment processes through continuous synchronization.

---

## links

- [Infrastracture](https://github.com/Oran901/infraRepo)
- [GitOps](https://github.com/Oran901/gitOpsRepo)
- [Application](https://github.com/Oran901/devopsAppPoke)

---

## About me

Hi, I’m Oran Yahud, a passionate DevOps enthusiast who thrives on all things tech and loves working in collaborative environments to build and create.

For any questions or feedback, feel free to reach out to me at: [oranya901@gmail.com]

