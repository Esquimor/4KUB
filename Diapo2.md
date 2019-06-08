# Installing kubernetes

## On the cloud

Google Cloud Platform (GCP):

- Dédicated platform => GKE
- Cloud le \+ facile
- Support HA
- web console ou CLI gcloud

Azure:

- Azure Container Service (AKS)
- = GCP
- autre que KUB

AWS:

- EKS

## On baremetal / from strach

Installation:

- K8s tout seul
- Own cloud-providers interfaces
- Créer un model réseau
- Manager le cluster

Kubespray => outil pour faciliter l'installation

## For local development

Solutions:

- Docker pour Mac/Windows = intégre kub
- Minikube = un seul noeud kub cluster dans VM 
  - VirtualBox
  - Kubectl
  - Minikube
- kubeadm = cluster
  - mini viable cluster
  - izi to use
  - Software:
    - chaque machine: Docker, Kubeadm, Kubelet
    - hôte: Kubectl

Voire les prérequis Kub

## Installing the Kubernetes dashboard

Interface web => manager cluster

Suivre procédure installation