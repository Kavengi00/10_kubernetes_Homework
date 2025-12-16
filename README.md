````md
# Kubernetes Homework – Lead Scoring Model

This repository contains my solution for the **Kubernetes homework** from the **Machine Learning Zoomcamp (2025)**.

In this project, a lead scoring model from Homework 5 is deployed to a local Kubernetes cluster using **kind** and **kubectl**.

---

## What was done

- Built a Docker image for the lead scoring model
- Tested the model locally using Docker
- Created a local Kubernetes cluster with kind
- Deployed the model to Kubernetes
- Exposed the deployment using a Service
- Tested the service using port forwarding
- Enabled Horizontal Pod Autoscaling (HPA)
- Observed automatic scaling under increased load

---

## Tools Used

- **:contentReference[oaicite:0]{index=0}**
- Docker
- kind
- kubectl
- Python

---

## How to Run

1. Build the Docker image:
```bash
docker build -f Dockerfile_full -t zoomcamp-model:3.13.10-hw10 .
````

2. Load the image into kind:

```bash
kind load docker-image zoomcamp-model:3.13.10-hw10
```

3. Apply Kubernetes configs:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

4. Forward the service port:

```bash
kubectl port-forward service/subscription 9696:80
```

5. Test the service:

```bash
python q6_test.py
```

---

## Author

**Nelly Alex**
Machine Learning Zoomcamp – 2025

```
