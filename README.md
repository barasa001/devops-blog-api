# DevOps Blog API
This project is a Node.js backend API for a blog application with authentication and CRUD operations for blog posts. The project includes a comprehensive DevOps pipeline for CI/CD, containerization, and deployment to an Azure server.

## Features
- Node.js backend API
- User authentication
- CRUD operations for blog posts
- CI/CD pipeline using GitHub Actions
- Docker containerization
- Deployment to Azure server
- Infrastructure as Code with Terraform

## Prerequisites
- Node.js and npm
- Docker
- Azure account
- GitHub repository with the following secrets:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`
  - `AZURE_SERVER_IP`
  - `AZURE_SERVER_USERNAME`
  - `AZURE_SERVER_SSH_KEY`

## Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/barasa001/devops-blog-api.git
   cd devops-blog-api

2. **Apply Terraform configuration:**

   ```bash
   terraform apply
### Deployment

The deployment to the Azure server is handled through the GitHub Actions workflow. Ensure that the necessary secrets are added to your GitHub repository.

The deployment steps are:

1. SSH into the Azure server
2. Install Docker (if not already installed)
3. Pull the latest Docker image
4. Stop and remove any existing Docker containers
5. Run the new Docker container

## Monitoring and Logging

### Monitoring
We use Prometheus to track application performance and health metrics. The metrics are exposed at `/metrics` endpoint.

### Logging
We use Winston for logging. Logs are collected and stored in `combined.log` and `error.log` files. In development mode, logs are also output to the console.

#### Configuration
- **Prometheus**: Make sure you configure Prometheus to scrape the `/metrics` endpoint of your application.
- **Winston**: Logs are automatically managed by the application. Ensure the log files are not exposed or public.

### Setting Up Prometheus and Grafana
- Install Prometheus and Grafana on your server.
- Configure Prometheus to scrape your application’s metrics endpoint.
- Integrate Grafana with Prometheus to visualize the metrics.

### Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some feature'`)
5. Push to the branch (`git push origin feature-branch`)
6. Create a new Pull Request

### Author
Seth Barasa - [GitHub Profile](https://github.com/barasa001)
