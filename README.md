# DevSecOps TicTacToe Demo Project

This project demonstrates a complete DevSecOps pipeline implementation using a simple TicTacToe game built with React, TypeScript, and Vite. It showcases modern DevSecOps practices with continuous integration, security scanning, and automated deployment.

## What is DevSecOps?

DevSecOps is an evolution of DevOps that integrates security practices into every phase of the software development lifecycle. While DevOps focuses on breaking down barriers between development and operations teams to enable faster delivery, DevSecOps goes a step further by making security an integral part of the development process rather than an afterthought.

Key differences between DevOps and DevSecOps:
- **DevOps**: Focuses on automation, continuous integration, and continuous delivery (CI/CD) to speed up development and deployment cycles.
- **DevSecOps**: Maintains the speed of DevOps while adding security checks and controls throughout the pipeline, including:

  - Code security scanning
  - Dependency vulnerability checks
  - Container security scanning
  - Infrastructure-as-Code security validation
  - Runtime security monitoring

## Project Overview

### Game Description
The project features a classic Tic-tac-toe game where:
- Two players take turns marking spaces on a 3×3 grid
- Players use X and O as their markers
- The first player to get three of their marks in a row (horizontally, vertically, or diagonally) wins
- If all squares are filled and no player has won, the game is a draw

### Game Screenshot
<img width="1472" height="829" alt="Application_Screenshot" src="https://github.com/user-attachments/assets/969b3f31-d54d-4722-b7ca-7433eeff74a8" />

### Project Structure
```
src/
├── components/
│   ├── Board.tsx       # Game board component
│   ├── Square.tsx      # Individual square component
│   ├── ScoreBoard.tsx  # Score tracking component
│   └── GameHistory.tsx # Game history component
├── utils/
│   └── gameLogic.ts    # Game logic utilities
├── App.tsx             # Main application component
└── main.tsx           # Entry point
```

## DevSecOps Architecture

<img width="1243" height="512" alt="DevSecOps Demo" src="https://github.com/user-attachments/assets/b0e0de45-1153-422c-818d-aac443151549" />


The architecture implements a comprehensive DevSecOps pipeline with the following stages:

1. **Development**:
   - Local development with React & TypeScript
   - Code quality checks with ESLint

2. **Version Control & CI (GitHub)**:
   - Code hosting and version control
   - Automated testing
   - Security scanning
   - Code quality analysis

3. **Container Registry**:
   - Image scanning
   - Vulnerability assessment
   - Image versioning

4. **Continuous Deployment**:
   - ArgoCD for GitOps
   - Automated deployments

5. **Production (Kubernetes)**:
   - Container orchestration
   - High availability
   - Auto-scaling

### This project implements a full DevSecOps pipeline with the following components

1. **Application Layer**:
   - React + TypeScript frontend
   - Vite for build optimization
   - ESLint for code quality

2. **Container Layer**:
   - Multi-stage Dockerfile for optimized builds
   - Nginx as the production web server
   - Trivy for container vulnerability scanning

3. **CI/CD Pipeline**:
   - GitHub Actions for CI/CD workflow
   - ArgoCD for GitOps-based deployments
   - Kubernetes for container orchestration

## Prerequisites to run the project locally

- Node.js (v20 or later)
- npm (Latest version)
- Docker 
- kubectl

### Running Locally without Docker

1. Clone the repository:
```bash
git clone https://github.com/Narasimha-Potturi/DevSecOps-Demo-Project.git
cd DevSecOps-Demo-Project
```

2. Install dependencies:
```bash
npm install
```

3. Start development server:
```bash
npm run dev
```

4. Build for production:
```bash
npm run build
```
### Running Locally with Docker

1. Clone the repository:
```bash
git clone https://github.com/Narasimha-Potturi/DevSecOps-Demo-Project.git
cd DevSecOps-Demo-Project
```

2. Build the Docker image:
```bash
docker build -t tic-tac-toe .
```

3. Run the Docker container:
```bash
docker run -p <HOST_PORT>:<CONTAINER_PORT> image_name
```
4. Access the application at `http://localhost:host_port`

## DevSecOps Pipeline Workflow

### 1. Continuous Integration (GitHub Actions)

Our CI pipeline (`CI-CD.yml`) includes the following stages:

a) **Test Stage**:
   - Runs unit tests
   - Validates code functionality

b) **Static Analysis**:
   - ESLint for code quality
   - TypeScript type checking
   - Security scanning

c) **Build Stage**:
   - Compiles TypeScript
   - Bundles application
   - Creates optimized production build

d) **Container Stage**:
   - Builds Docker image
   - Scans container for vulnerabilities
   - Pushes to GitHub Container Registry

### 2. Continuous Deployment (ArgoCD)

The CD process is handled by ArgoCD, implementing GitOps principles:

1. **ArgoCD Setup**:
   - Monitors the Kubernetes manifests in the `kubernetes/` directory
   - Automatically syncs changes to the cluster
   - Ensures desired state matches actual state

2. **Deployment Strategy**:
   - Uses rolling updates for zero-downtime deployments
   - Implements health checks and readiness probes
   - Automatically scales based on demand

### 3. Kubernetes Configuration

The application is deployed to Kubernetes with the following specifications:

- 3 replicas for high availability
- Resource limits and requests defined
- Liveness and readiness probes configured
- Automatic container registry secret management


### Prerequisites for Deployment:
1. A Kubernetes cluster
2. ArgoCD installed on the cluster
3. Access to GitHub Container Registry

## Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/AmazingFeature`
3. Commit your changes: `git commit -m 'Add some AmazingFeature'`
4. Push to the branch: `git push origin feature/AmazingFeature`
5. Open a Pull Request
6. Submit your changes





















