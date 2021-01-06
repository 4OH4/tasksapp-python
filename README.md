# tasksapp-python

Template app for Python-MongoDB integration in Docker and Kubernetes.

This repository consists of files that are explained better in this article: https://medium.com/@varunkumar032/deploy-your-first-flask-mongodb-app-on-kubernetes-8f5a33fa43b4

## Google Cloud GKE initial setup

From command line, with [Google Cloud SDK](https://cloud.google.com/sdk/docs/install) installed:

    gcloud components install kubectl

    gcloud config set project MyProjectName
    gcloud config set compute/zone europe-west2-a

Create a cluster and get credentials for `kubectl`:

    gcloud container clusters create MyClusterName --num-nodes=1
    gcloud container clusters get-credentials MyClusterName

## Kubernetes deployment

    kubectl apply -f tasksapp.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-pv.yaml
    kubectl apply -f mongo-pvc.yaml

## Teardown

    kubectl delete deployment tasksapp
    kubectl delete deployment mongo
    kubectl delete svc tasksapp-svc
    kubectl delete svc mongo

## Google Cloud clean-up

    gcloud container clusters delete MyClusterName

** Check all resources have been deleted in the console - if in doubt, delete the project as well **
