# Jenkins Pipeline for Docker Image Build and Vulnerability Scanning

## Project Overview
This project is a Jenkins pipeline designed to automate the process of building Docker images and scanning them for vulnerabilities using Trivy. The pipeline integrates Docker and Trivy to identify critical vulnerabilities, enabling proactive security measures in the CI/CD workflow. Additionally, the pipeline includes automated email notifications to alert stakeholders if any high or critical severity vulnerabilities are detected.

## Features
- **Automated Docker Image Build**: The pipeline builds a Docker image from the specified Dockerfile in the repository.
- **Vulnerability Scanning**: Trivy scans the built Docker image for vulnerabilities, filtering for high and critical severity issues.
- **Email Notification**: Automated email notifications alert stakeholders of any vulnerabilities, ensuring timely action and compliance with security standards.
- **Parameterization**: The pipeline allows parameter inputs to customize the Docker image build, such as specifying the image name.

## Technologies Used
- **Jenkins**: CI/CD automation server.
- **Docker**: Containerization tool for building images.
- **Trivy**: Open-source vulnerability scanner for container images.
- **Groovy**: Language for scripting Jenkins pipeline.

## Pipeline Stages
1. **Build Docker Image**: 
   - Builds the Docker image based on the `Dockerfile` present in the repository.
   - Parameterized to accept different image names based on the user’s input.
2. **Vulnerability Scan**:
   - Scans the built Docker image using Trivy to identify any security vulnerabilities, specifically high-severity issues.
   - Saves the results as a JSON file (`vulnerabilities.json`).
3. **Email Notification**:
   - If any high or critical vulnerabilities are found, sends an email notification with the scan report attached for immediate action.

## Configuration
1. **Jenkins Setup**:
   - Install plugins: Docker Pipeline, Trivy, Email Extension, etc.
   - Configure SMTP server in Jenkins for email notifications.

2. **Environment Variables**:
   - Configure necessary environment variables by referencing the provided `config-sample.env` file.
