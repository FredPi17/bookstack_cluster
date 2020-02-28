#HOW TO DEPLOY

##SWARM

Tout d'abord il faut lier les différents serveurs ensemble avec swarm: https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/ 

Puis créer les dossiers où seront stockés les fichiers à synchroniser avec les services sur les différents serveurs:
(ces commandes sont à exécuter sur tous les noeuds du cluster swarm)

`mkdir -p ~/bookstack/storage
mkdir -p ~/bookstack/uploads`

Puis exécuter le docker-compose.yml:

`docker stack deploy cluster --compose-file docker-compose.yml`

De base, le docker-compose permet de créer un seul réplica de chaque service. 

Pour mettre à jour un service, exécuter cette commande: 

`docker service update <nom_du_service>`

Pour modifier le nombre de réplicas d'un service, exécuter:

`docker service update --replicas <nombre> <nom_du_service>`


