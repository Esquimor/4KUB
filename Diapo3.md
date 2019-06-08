# Running applications on Kubernetes

## Pods

pods => cellule Kub

pod = 1 ou plusieurs containers

- même namespace
- peuvent partager même storage

Application peut = plusieurs containers: container à besoin d'un autre container => composite containers

Cycle de Vie:

- Pending: accepter par le cluster
  - unknow: peut pas accéder au pod
  - running
    - success
    - fail

start (dev) = $ kubectl run <container>

Pod descrit dans Pod manifest => peut versionner pod

$ kubectl apply -f <manifest>

Manifest structure:

- Api version
- kind of resource
- metadata
- spécification du pod



## ConfigMap and Secrets

Permettre des paramètres dynamiques

ConfigMap = Map de données

Secret = même mais hasher

kubectl => créer config map 

$ kubectl create configmap app-config <name>=<value>

utilisation: $(<name>)

secret:

$ kubectl create secret  docker-registry pull-secrets <name>=<value>



## ReplicaSets

Marcher des réplicas de pods au nb indiquer

=> améliore les performances

Indiquer le pod à répliquer à la création du réplica

Pas utiliser dans les clusters => préfèrer deployments

## Deployments

Deployment => K8s Obejct pour gérer les pods dans le cluster

Réduit le risque d'erreur

Deployment = 1 ou n replica set

Rollback besoins de plusieurs replica set

Best pratice

Manifest:

- kind: Deployment
- spec:
  - nb replicas
  - pod to use
  - pods template
  - strategy: comment update
    - Recreate: kill all et create all
    - RollingUpdate: kill et create au fur et à mesure en % ou nb
      - maxUnavailble: cb pod peuvent être down
      - maxSurge: cb pod peuvent être créer

## Jobs

Job = one shot process

Créer un ou n pods est s'assure que x pods sont créer

Manifest:

- kin: Job

Les containers ne seront pas auto redémarrer

## DaemonSets

DaemonSet => responsable pour faire marcher les pods sur les nodes

Deployments = meilleur solution

Utilisation:

- Log
- Storage cluster
- Monitoring daemon

Exemple: Fluentd

## Namespaces

Namespaces = cluster virtuel dans un cluster

- Deployer des app avec le même nom
- Quota pour équipe/projet
- Organiser le cluster

3 namespaces:

- Default: si namespace non défini
- Kube-system: namespace pour Kubernetes system
- Kube-public: Visible par tout les utilisateurs

