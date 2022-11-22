Azad Rojoa
- consignes :
    Pour chaque étape il faut produire les fichiers YAML nécessaires et les conserver pour les communiquer lors du rendu.

    - Créer un Pod pour déployer l'image registry.cluster.wik.cloud/public/echo (c'est l'image créée lors du TP WIK-DPS-TP02) et le tester sur minikube en local
        - Pour le tester vous devez faire un port-forwarding entre le port du Pod sur lequel votre API écoute et un port sur votre hôte
    - Remplacer le Pod par un ReplicaSet afin de déployer 4 réplicas du Pod créé précédemment
    - Remplacer le ReplicaSet par un Deployment afin de pouvoir définir une stratégie d'update en   RollingRelease (50% en maxUnavailable)
    - Créer un Service pour pouvoir communiquer avec les Pod du ReplicaSet créé précédemment
        - Pour le tester vous devez faire un port-forwarding entre le port du Service sur lequel votre API écoute et un port sur votre hôte
    - Activer le plugin ingress nginx sur minikube et créer un Ingress (nom de domaine au choix) pour communiquer avec le Service créé précédemment.

    - Tester en ajoutant le nom de domaine choisi dans /etc/hosts afin de résoudre localement vers le service nginx de minikube
        - Vous pouvez alors accéder via votre navigateur au service créé précédemment
        - Faites une capture d'écran de la page sur votre navigateur avec le nom de domaine de votre choix pour votre service

    

- Lancer les fichier:

    - minikube start
    - kubectl apply -f (nom du fichier)
    - kubectl port-forward service/my-service 8080:80 (sauf pour ingress.yaml)
    - gougueule.com/ping