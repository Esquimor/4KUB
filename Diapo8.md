# Monitoring, Logging and Backups

## Simple monitoring using kube-prometheus

sysadmin => vue d'ensemble du cluster et des app dessus

être proactif et planifier les besoin

Prometheus: Database chronologique

- Watch de lui même les app
- use PromQm
- voir graph et alert PromDash

Utiliser kube-prometheus pour monitorer Kub

- Install Prometheus
- custom resource definition (CRD's)
- label des services ciblés
- combine avec
  - Prometheus node-exporter: info sur le physique
  - kube-state-metrics: Kub api
  - Grafana: voir les données en web

C'est un ServiceMonitor

## Managing logs inside the cluster

Besoin de manager les logs des n pods

Besoin de filtrer les différents logs

Utiliser log aggregation: Fluentd



## Backing up the cluster with Heptio Velero

Besoin d'une solution pour backup le cluster