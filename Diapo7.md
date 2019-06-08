# Introduction to Helm

## Why helm

Helm = package manager pour kub

- Créer un packer de yaml pour des app kub complexes
- package = charts
  - Facilement customisable
  - Facielement partagable

Helm rend la gestion des objects dans le cluster facile

Prod:

- Service upgrade
- rollback
- Custom hook

Composants:

- Server composant: Tiller
- Client composant pour appeler Tiller

## Using helm

Helm community => officiel chart repository

Modes:

- Stable: considérer comme prod ready
- Incubator: Instable

Pour l'installation de chart merci de se reporter à leur doc

## Creating your own charts

helm cli => command pour créer des chart

Chart.yaml => toutes les informations sur le chart

values.yaml => tous les paramètres du chart

requirements.yaml => agit comme les dépendances



Pour utiliser les variables => {{ .myVar }}



- Chart.yaml
- charts
- templates
  - NOTES.text
  - _helpers.tpl
  - deployment.yaml
  - ingress.yaml
  - service.yaml
- values.yaml