#  Static Web App with Docker & Kubernetes

This project demonstrates a complete workflow for containerizing and deploying a simple static HTML web server using **Docker** and **Kubernetes** on an Ubuntu environment.

---

##  What’s Included?

- index.html: A simple static web page
- Dockerfile: Containerizes the app with Nginx
- deployment.yaml: Kubernetes Deployment for Nginx
- service.yaml: Kubernetes Service to expose the app

---

## Steps to Deploy

###  Build Docker Image

```bash
docker build -t yourusername/nginx-app .

docker run -d -p 8080:80 yourusername/nginx-app

Access in browser: http://localhost:8080

Push to dockerhub:
docker login
docker push yourusername/static-web-app:latest

☸️ Deploy to Kubernetes:
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
Access via NodePort: http://localhost:<nodePort>

🧹 Cleanup
kubectl delete -f deployment.yml
docker rmi yourusername/nginx-app

