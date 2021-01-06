# tasksapp-python

Template app for Python-MongoDB integration in Docker and Kubernetes.

This repository consists of files that are explained better in this article: https://medium.com/@varunkumar032/deploy-your-first-flask-mongodb-app-on-kubernetes-8f5a33fa43b4

## Kubernetes deployment

    kubectl apply -f tasksapp.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-pv.yaml
    kubectl apply -f mongo-pvc.yaml
