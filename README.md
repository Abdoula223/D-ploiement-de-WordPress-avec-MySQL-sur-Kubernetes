Déployez wordpress en suivant les étapes suivantes
Créez un deployment mysql avec un seul replicat
Créez un service de type clusterIP pour exposer vos pods mysql
Créez un deployment wordpress avec les bonnes variables d’environnement pour se connecter à la base de données mysql
Votre deployment devra stocker les données de wordpress sur un volme mounté dans le /data de votre nœud
Créez un service de type nodeport pour exposer le frontend wordpress!
# D-ploiement-de-WordPress-avec-MySQL-sur-Kubernetes

Déploiement de WordPress avec MySQL sur Kubernetes

Ce projet explique comment déployer WordPress avec une base de données MySQL sur Kubernetes. Les données de MySQL sont persistantes grâce à l'utilisation d'un PersistentVolume (PV) et d'un PersistentVolumeClaim (PVC), tandis que WordPress est exposé à l'extérieur du cluster via un service de type NodePort.
Prérequis

    Un cluster Kubernetes fonctionnel.

    kubectl installé et configuré pour interagir avec le cluster.

    Accès à un nœud Kubernetes pour stocker les données de WordPress (via hostPath).

Structure du projet

Le projet est composé des fichiers YAML suivants :

    MySQL

        mysql-pv.yaml : Définit un PersistentVolume pour MySQL.

        mysql-pvc.yaml : Définit un PersistentVolumeClaim pour MySQL.

        mysql-deployment.yaml : Déploie MySQL avec un seul replica et utilise le PVC pour la persistance.

        mysql-service.yaml : Expose MySQL en interne via un service de type ClusterIP.

    WordPress

        wordpress-deployment.yaml : Déploie WordPress et le connecte à MySQL via des variables d'environnement.

        wordpress-service.yaml : Expose WordPress à l'extérieur du cluster via un service de type NodePort.


Auteur

abdoulaye Diallo
email:agabdoulaye16@gmail.com
Licence
