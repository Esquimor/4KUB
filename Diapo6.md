# Running stateful applications on Kubernetes

## Stateful applications at scale

stateful = application avec des sessions pour l'utilisateur

stateless = ne maintient aucune information

Scaler une app stateless = facile => ajouter plus d'instance avec un load balancer

Scaler une app stateful = difficile

- Besoin de refactoriser les données partager entre les instances
- Besoin de vérifier que les éléments démare dans le bonne ordre

## StatefulSet

StatefulSet => apporte de la valeur ajouté pour les app:

- Stable, identifiant réseau unique
- Stable, persistence des données
- Ordered, voire diapo



Pour exposer un objet StatefulSet => besoin d'un service headless = spec.clusterIp: None