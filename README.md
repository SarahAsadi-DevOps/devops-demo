# DevOps Demo Project 

This is my first DevOps practice project created to learn and experiment with modern DevOps tools and workflows.

The project demonstrates a simple static web application (HTML) containerized with Docker and deployed to Kubernetes using Minikube, with CI/CD implemented via GitHub Actions.

---

## 🛠 Technologies Used

- Git
- GitHub
- Docker
- Kubernetes
- Minikube
- GitHub Actions
- Nginx

---

##  Project Structure
```bash
.
├── Dockerfile
├── index.html
├── .github/workflows/main.yml
└── k8s/
├── deployment.yaml
└── service.yaml


##  How to Run
1. **Docker**: `docker build -t devops-demo .`
2. **Run**: `docker run -p 8080:80 devops-demo`
3. **K8s**: `kubectl apply -f k8s/`

##  Author
**Sarah Asadi**

