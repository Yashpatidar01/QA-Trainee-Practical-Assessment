# Accuknox QA Trainee Practical Assessment

## Problem Statement 1: Containerization and Deployment of Wisecow Application on Kubernetes

### Title: Containerization and Deployment of Wisecow Application on Kubernetes

**Project Repository:** [Wisecow App Repository](https://github.com/nyrahul/wisecow)

### Objective
The goal is to containerize and deploy the Wisecow application on a Kubernetes environment with secure TLS communication.

### Requirements

#### 1. Dockerization
- Developed a `Dockerfile` for creating a container image of the Wisecow application.

#### 2. Kubernetes Deployment
- Created Kubernetes manifest files for deploying the Wisecow application in a Kubernetes environment.
- Exposed the Wisecow app as a Kubernetes service for accessibility.

#### 3. Continuous Integration and Deployment (CI/CD)
- Implemented a GitHub Actions workflow for:
  - Automating the build and push of the Docker image to a container registry whenever changes are committed.
  - Automatically deploying the updated application to the Kubernetes environment following successful image builds.

#### 4. TLS Implementation
- Ensured that the Wisecow application supports secure TLS communication.

### Expected Artifacts
- A private GitHub repository containing:
  - The Wisecow application source code.
  - The `Dockerfile` for the application.
  - The Kubernetes manifest files for deployment.
  - The CI/CD pipeline configuration.
  - A GitHub Actions workflow file for facilitating Continuous Build and Deployment (CI/CD).

### Access Control
- The GitHub repository is set to public.

### End Goal
Successfully containerized and deployed the Wisecow application to the Kubernetes environment with an automated CI/CD pipeline and secured with TLS communication.

---

## Problem Statement 2: Scripting Objectives

### Objective Selection
The following two objectives were chosen for implementation using Python:

1. **System Health Monitoring Script**
2. **Application Health Checker**

### 1. System Health Monitoring Script
Developed a Python script that monitors the health of a Linux system. The script checks:
- CPU usage
- Memory usage
- Disk space
- Running processes

If any metrics exceed predefined thresholds (e.g., CPU usage > 80%), the script logs an alert to the console.

#### Code Example:
```python
import psutil
import logging

# Set up logging
logging.basicConfig(filename='system_health.log', level=logging.INFO)

def check_system_health():
    cpu_usage = psutil.cpu_percent()
    memory_info = psutil.virtual_memory()
    disk_info = psutil.disk_usage('/')

    if cpu_usage > 80:
        logging.warning(f'High CPU Usage: {cpu_usage}%')
    if memory_info.percent > 80:
        logging.warning(f'High Memory Usage: {memory_info.percent}%')
    if disk_info.percent > 80:
        logging.warning(f'Low Disk Space: {disk_info.percent}%')

if __name__ == "__main__":
    check_system_health()
