# Networking on Kubernetes

## Labels and annotations

label = key/value => attacher à un object Kub

Couplé au selecteur, les labels sont un outil puissant

A utiliser pour toutes les informations sur les objets

Selecteur:

- Equality-based: =, ==, !=
- Set-based: in, notin, exists

Annotation = key/value pour Kub resources

Annotation = non identifiable element

## Services

Pod = element éphémere

Service = abstraction au pod et les régles qui leurs sont associès

4 types de services:

- ClusterIp: exposer les pods avec une IP interne au cluster =/= exterieur du cluster
- LoadBalancer: Cloud seulement, load balancing entre les pods
- NodePort: associe un port à un port
- ExternalName: système de redirection = proxy

## Ingress

Ingress = objet permet de gérer les accès extérieur aux services du cluster

Ingress à besoin d'un Ingress controlleur

Manifest = gérer avec spec.rules

Ingress Controller:

- Check new Ingress
- Applique les régles
- Reload le service

Type de controller:

- GCE-ingress: load balncer externe
- Nginx-ingres: utiliser Nginx
- D'autres sont disponnibles

## Networking solutions

Pod ont une ip associé

Kub 2 type de plugin réseau:

- CNI: Container Network Interface
  - CNCF projet
  - spec pour écrire des config réseau dans les LXC
  - Permet d'ajouter bcp de plugin CNI: Flannel, Calico, Weave Net, Canal
- Kubenet: depreceated

## Service discovery

ClusterIp = expose un service sur le cluster (microservice)

2 types:

- Env Var:
  - Kub ajout des env au service actif
- DNS
  - Solution \+ utiliser
  - Addon => watch new Services et update sa table de recors

## Network policies

Network policies => comment les pods communiquent entre eux

Default: pod accepte tous

Avec un Network policy => accepte que les spécifiées