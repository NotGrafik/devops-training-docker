# TP Pablo Jean Louis B3C

## Questions 3:

### 3.a
Récupérer l'image sur le docker hub
```bash
docker pull nginx
```

### 3.b
Utilisez une commande pour vérifier que l'on dispose bien de l'image en local
```bash
docker images
```

### 3.d
Démarrer un nouveau container et servir la page html que nous venons de créer.
```bash
docker run --name hello-world-container -d -p 80:80 -v /chemin/vers/mon-repo-local/html:/usr/share/nginx/html nginx
```

### 3.e
Supprimer le container.
```bash
docker rm hello-world-container
```

### 3.f
Relancez le même container sans l'option '-v', utiliez la commande cp pour servir le fichier.
```bash
docker run --name hello-world-container -d -p 80:80 nginx
docker cp /chemin/vers/mon-repo-local/html hello-world-container:/usr/share/nginx
```

## Questions 4:

### 4.a
À l'aide d'un Dockerfile, créez une image qui permet d'exécuter un server Web.
```bash
docker build -t nginx-image .
```

### 4.b
Exéctuez cette nouvelle image
```bash
docker run --name nginx-container -p 8080:80 nginx-image  
```

### 4.c
Voici les avantages et inconvénients de COPY / MOUNT VOLUME

#### Copy:
##### Avantages:
###### Pratique pour le développement, pas besoin de reconstruire une image à chaque fois.
##### Inconveniants:
###### Moins portable et performant, dépend de la configuration de la machine de l'hôte.

#### Mount Volume:
##### Avantages:
###### Autonome et portable, pas de dépendances aux système de fichiers de l'hôte, idéal pour le déploiement en production.
##### Inconvéniants:
###### Pas très pratique pour les itérations rapide en dev, reconsutruction obligatoire à chaque changement de fichiers.
