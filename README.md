# myapp

# Containerization and Deployment with Red Hat Podman, Kubernetes, GitHub, and SonarQube

## Objectives
This guide will walk you through the process of:
- Containerizing applications using Red Hat Podman.
- Deploying containerized applications to a Kubernetes cluster.
- Leveraging GitHub for version control.
- Integrating SonarQube into your CI/CD pipeline for code quality and vulnerability analysis.

## Prerequisites
- **Red Hat Podman** installed on your local machine.
- **Minikube** or **OpenShift** installed and configured.
- **GitHub** account for version control and CI/CD.
- **SonarQube** instance (open-source) for code quality checks.
- A sample application for hands-on exercises (e.g., a simple Python Flask app or Node.js app).

## 1. Containerization with Red Hat Podman

### 1.1 Write a Dockerfile
Create a `Dockerfile` in the root directory of your sample application. Below is an example for a Python Flask application:

```Dockerfile
# Use the official Python image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy the current directory contents into the container
COPY . .

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define the command to run the application
CMD ["python", "app.py"]

