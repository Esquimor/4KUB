# Storage on Kubernetes

## Volumes

filesystem => éphemère, liée au container: Pareil avec Kub

Kub =/= Docker volumes

- Docker: Directory monté sur le machine hôte
- Kub: volume à un lifetime = celui du pod
  - pod crashes: garde data
  - pod détruit: data perdu

Cas d'utilisation:

- Intra-pod communication: partager les données entre deux container
- Intra-node: accéder à un fichier du noeud

Kub supporte bcp de type de volumes: Bfs, Iscsi, Cephfs, AzureDisk, etc...

Manifest: 

- use spec.volumes pour provisionner
- use spec.containers.volumeMounts pour monter

## Persistent Volumes

Container volumes = bad

Utiliser PersistentVolume

2 types de resources:

- PersistentVolume
  - un espace de stockage utilisable par un pod
  - indé du pod/container
  - spec.accessMode: ReadWriteMany = plusieurs noeuds peuvent écrire
- PersistentVolumeClaim
  - Usage exclusif d'un persitentVolume par un Pod

## Dynamic Volume Provisioning

Pour dynamiser les volumes de stockage: Kub a besoin du'n StorageClass et d'un PersistentVolumeClaim

