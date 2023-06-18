# Argo CD Flask Deployment

This project contains a simple Flask application that is deployed to a Kubernetes cluster using Argo CD. The Flask application provides two endpoints, the root endpoint that returns "Hello World! Deployed using Argo CD!" and the '/around' endpoint that returns "Isn't Argo CD pretty amazing?".

## Table of Contents

- [Project Structure](#project-structure)
- [Local Setup](#local-setup)
- [Deploying with Argo CD](#deploying-with-argo-cd)
- [Contributing](#contributing)
- [License](#license)

## Project Structure

- `Dockerfile`: Builds a Docker image of the Flask application.
- `main.py`: The Flask application source code.
- `requirements.txt`: Lists the Python dependencies.
- `deployment.yaml`: Configures the Kubernetes deployment.
- `service.yaml`: Configures the Kubernetes service.

## Local Setup

To build and run the application locally:

1. **Build the Docker image**
   ```bash
   docker build -t hello-app .
