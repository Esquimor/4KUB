# Introduction to containers orchestration

## Containers orcherstration

Docker permet de créer/démarre/stoper des containers.

Mais il atteind des limites pour la production

Prod Env:

- Checker la santé des containers
- permettre services discovery
- intégrer new version
- scaler

Orchestrateur automatise la gestion des containers

- Start/stop container
- service discovery
- load balancer
- gére les secrets
- manage les container

## Immutable infrastructure

Infrastructure traditionel:

- System admin => fait à la main les différentes actions
- Changement Incrémential
- Servers sont mutable

Immutable système

- Aucune modification
- Remplace les serveurs
- Simple appel API

Container et orcherstrateur => organiser autour du système immuable

Rollback plus facile

## Orcherstration softwares

Docker swarm mode

Nomad

Kubernetes

Apache Mesos

AWS ECS

Cattle

## Why kubernetes ?

Création 2014 Chez google, 2015 CNCF

Cloud Native Computing Foundation

- Foundation open source
- Plusieurs groupes l'a gère
- 14 projets

Kubernetes= solution de management de containers

- configuration: YAML ou JSON
- Api et méthodes pour la gestion d'application
- autogérer
- Open source
- Dev en Go

Solution Cloud déployable partout

## Kubernetes architecture

Components:

- Server Master: controle le cluster. Components:
  - Kube-apiserver: kub api
  - Kube-scheduler: intégre new container
  - Etcd: Cluster data
  - kube-controller-manager: regarde état container
  - cloud-controller-manager: travail avec le cloud provider

- Node Server: worker => container run
  - kubelet: gére les pods
  - kube-proxy: régle réseau sur l'hôte

Docker est le container par défault.