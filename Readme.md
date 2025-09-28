# Git Lab-1

![GitHub repo size](https://img.shields.io/github/repo-size/KalharaBatangala/git-lab1?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/KalharaBatangala/git-lab1?style=flat-square)
![Jenkins](https://img.shields.io/badge/Jenkins-Pipeline%20as%20Code-blue?style=flat-square&logo=jenkins)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=flat-square&logo=docker)


## Overview

This repository serves as a hands-on learning project for integrating GitHub with Jenkins using Pipeline-as-Code (PaC). The project demonstrates a simple CI/CD pipeline running Jenkins in a Docker container. It includes basic stages for building, testing, and deploying a minimal web application consisting of an `index.html` file and an optional `app.js` script.



Key technologies:
- **GitHub**: For version control and repository management.
- **Jenkins**: CI/CD automation.
- **Docker**: To containerize the Jenkins environment.



## Setup and Installation

1. **Clone the Repository**:
   ```
   git clone https://github.com/KalharaBatangala/git-lab1.git
   cd git-lab1
   ```

2. **Run Jenkins in Docker**:
   Ensure Docker is installed on your system. Pull and run the Jenkins Docker image:
   ```
   docker run -d -p 8080:8080 -p 50000:50000 --name jenkins -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
   ```
   - Access Jenkins at `http://localhost:8080`.
   - Follow the setup wizard to unlock Jenkins and install recommended plugins.

3. **Configure Jenkins for GitHub Integration**:
   - Install the GitHub plugin in Jenkins.
   - Create a new pipeline job and point it to this repository's `Jenkinsfile`.
   - Set up a webhook in GitHub (Settings > Webhooks) to trigger builds on push events.

## Jenkins Pipeline

The `Jenkinsfile` defines a declarative pipeline with three stages:

- **Build**: Simulates a build process and echoes "Build Success".
- **Test**: Simulates testing and echoes "Test Success".
- **Deploy**: Simulates deployment and echoes "Deploy Success".

