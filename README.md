# CI/CD with Jenkins and Kubernetes

This project is designed with Continuous Integration/Continuous Deployment (CI/CD) in mind using Jenkins, Kubernetes, GitLab, and Docker Hub.

- Jenkins
- Kubernetes
- GitLab
- Docker Hub

## Getting Started

Clone this repository:

```bash
git clone https://github.com/nisibz/CICD-Jenkins-Kubernetes.git
cd CICD-Jenkins-Kubernetes
```

## Building Docker Image

Build your Docker image using the following command:

```bash
docker build -t <your_docker_hub_username>/<your_project> .
```

Push the Docker image to Docker Hub:

```bash
docker push <your_docker_hub_username>/<your_project>
```

## Kubernetes Deployment

Before deploying, you need to make sure that the image name in `kubernetes/deployment.yaml` matches the one you have pushed to Docker Hub.

Open `kubernetes/deployment.yaml` and replace the `image:` value with the name of your Docker image.

To deploy your application to Kubernetes, run the following command:

```bash
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yml
```

## Further Steps and Explanation

For a detailed walkthrough of the project and its implementation, you can find step-by-step guides on my Medium page at https://medium.com/@bz.nantachai/ci-cd-with-jenkins-kubernetes-8c89046f2a3c.
