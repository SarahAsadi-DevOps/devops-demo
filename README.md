# DevOps Demo Project

This project is a small but complete DevOps workflow that demonstrates containerization, CI/CD automation, and Kubernetes deployment using a simple static web application.

The focus of this project is not on application complexity, but on understanding and implementing a basic but realistic DevOps pipeline.

---

## 🔧 Tech Stack

- **Version Control**: GitHub
- **CI/CD**: GitHub Actions
- **Containerization**: Docker
- **Container Registry**: DockerHub (`sarahasadi/devops-demo`)
- **Orchestration**: Kubernetes (tested with Minikube)
- **Web Server**: Nginx (serving a static HTML page)

---

## 🚀 High-level Workflow

1. **Code Push**  
   When I push changes to the `main` branch, GitHub Actions is triggered.

2. **Build & Push Docker Image**  
   The CI pipeline:
   - Logs in to DockerHub using GitHub Secrets  
   - Builds a Docker image for the application  
   - Tags it as `sarahasadi/devops-demo:latest`  
   - Pushes the image to DockerHub

3. **Kubernetes Deployment**  
   Kubernetes pulls the image from DockerHub and deploys it using:
   - A `Deployment` with **2 replicas** (for basic high availability)  
   - A `Service` of type `LoadBalancer` to expose the application

4. **Health Checks & Resources**  
   The Deployment includes:
   - **Readiness probe** to ensure the pod is ready before receiving traffic  
   - **Liveness probe** to restart the container if it becomes unhealthy  
   - **Resource requests/limits** to avoid resource overuse

---

## 📁 Project Structure
```text
.
├── Dockerfile
├── docker-compose.yaml
├── index.html
├── k8s
│   ├── deployment.yaml
│   └── service.yaml
└── .github
└── workflows
└── main.yml


