# TP Pablo Jean Louis B3C
## Questions 3:
### 3.a
Récupérer l'image sur le docker hub
```
docker pull nginx
```

### 3.b
Utilisez une commande pour vérifier que l'on dispose bien de l'image en local
```
docker images
```

### 3.d
Démarrer un nouveau container et servir la page html que nous venons de créer.
```
docker run --name hello-world-container -d -p 80:80 -v /chemin/vers/mon-repo-local/html:/usr/share/nginx/html nginx
```

### 3.e
Supprimer le container.
```
docker rm hello-world-container
```

### 3.f
Relancez le même container sans l'option '-v', utiliez la commande cp pour servir le fichier.
```
docker run --name hello-world-container -d -p 80:80 nginx
docker cp /chemin/vers/mon-repo-local/html hello-world-container:/usr/share/nginx
```