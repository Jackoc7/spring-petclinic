# Spring PetClinic — DevSecOps Pipeline

This repository demonstrates a secure CI/CD pipeline for building and deploying a Java application using GitHub Actions and the JFrog Platform.

## Overview

Spring PetClinic is a sample Spring Boot application used here as the basis for a DevSecOps pipeline demonstration. The pipeline compiles the code, runs tests, packages the application as a Docker image, and pushes it to JFrog Artifactory — with all dependencies resolved securely through JFrog rather than directly from the internet.

## Repository Structure

- .github/workflows/ci.yml — GitHub Actions CI pipeline
- Dockerfile — Multi-stage Docker build
- src/ — Application source code
- pom.xml — Maven build configuration

## CI Pipeline

The pipeline is triggered on every push or pull request to main and runs the following steps:

1. Compile — builds the source code via Maven
2. Test — runs the existing test suite
3. Package — produces a runnable JAR
4. Docker build and push — builds a Docker image and pushes it to JFrog Artifactory

All Maven dependencies are resolved through JFrog Artifactory (maven-central-remote), ensuring a secure and auditable software supply chain.

## Prerequisites

- Java 17+
- Maven
- Docker

## Running Locally

Clone the repository:

    git clone https://github.com/Jackoc7/spring-petclinic.git
    cd spring-petclinic

Run the application:

    ./mvnw spring-boot:run

The app will be available at http://localhost:8080

## Running via Docker

Pull the image from JFrog Artifactory: