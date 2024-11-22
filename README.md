- Avoir un compte github
- De préférence, avoir un éditeur de code (ex: VS Code)

## Etapes à suivre :
## TP DevOps
### I - Git clone et exécution
1) Faire un fork de ce [projet](https://github.com/HMP-DSO/Formation-DSO) vers votre répository Head Mind.
2) Cliquer sur code (bouton vert), dans HTTPS copier l'URL (.git) et aller dans votre invite de commande et taper la commande :
```
git clone [URL .git]
```
3) Ouvrez le fichier requirements.txt et vérifier que la version de PyYAML est bien la 5.3 "PyYAML==5.3". (Si besoin taper: pip install pyyaml==5.3)
4) Avec python, exécutez :
```
pip install -r requirements.txt
.\application.py
```
### II - Modification du code
5) Créer une nouvelle branch 'dev' et aller dessus
```
git branch dev
git checkout dev
```
6) La vulnérabilité que l'on vient d'exploiter a été corrigée dans la version PyYAML 5.3.1.
Tapez les commandes suivantes pour mettre à jour la dépendance et mettre à jour le fichier requirements.txt. 
```
pip install pyyaml==5.3.1
.\update_requirements.py
```
7) Envoyer le code vers la branch dev que vous venez de créer.
```
git add .
git commit -m "first commit dev"
git push
```
8) Aller dans github et vérifiez que la version de PyYAML dans la branch dev est bien en 5.3.1 alors que dans la branch main elle n'est encore que en 5.3.
9) Faire un merge de la branch dev vers la branch main
```
git merge [branch]
``` 
10) Vérifier alors que dans la branch main, la valeur de PyYAML est bien 5.3.1
## TP DevSecOps 1

### I - Préparation de l'environnement
1) Faire un fork de ce [projet](https://github.com/HMP-DSO/Formation-DSO) vers votre répository Head Mind.
@@ -24,49 +74,60 @@ git clone [URL .git]

### II - Découverte et test de l'application

2) Ouvrez le fichier requirements.txt et vérifier que la version de PyYAML est bien la 5.3 "PyYAML==5.3". (Si besoin taper: pip install pyyaml==5.3)
3) Ouvrez le fichier requirements.txt et vérifier que la version de PyYAML est bien la 5.3 "PyYAML==5.3". (Si besoin taper: pip install pyyaml==5.3)

3) Avec python, exécutez :
4) Avec python, exécutez :
```
pip install -r requirements.txt
.\application.py
```

4) Allez sur le navigateur et dans la barre de navigation tapez "127.0.0.1:5000". Vous devriez tomber sur un site web d'analyse de fichier de configuration 
5) Allez sur le navigateur et dans la barre de navigation tapez "127.0.0.1:5000". Vous devriez tomber sur un site web d'analyse de fichier de configuration 

5) Dans l'onglet "Upload", sélectionnez et upload le fichier "payload.yaml". Regardez alors votre terminal. La commande "dir" s'est exécutée et vous pouvez voir la liste des fichiers et dossiers de votre répertoire. Cela veut donc dire que la vulnérabilité a bien été exploitée.
6) Dans l'onglet "Upload", sélectionnez et upload le fichier "payload.yaml". Regardez alors votre terminal. La commande "dir" s'est exécutée et vous pouvez voir la liste des fichiers et dossiers de votre répertoire. Cela veut donc dire que la vulnérabilité a bien été exploitée.
Avec CTRL+C il est possible d'arréter l'exécution de l'application dans votre terminal. 

### III - Correction de la vuln

5) Créer une nouvelle branch 'dev' et aller dessus
7) Créer une nouvelle branch 'dev' et aller dessus
```
git branch dev
git checkout dev
```

6) La vulnérabilité que l'on vient d'exploiter a été corrigée dans la version PyYAML 5.3.1.
8) La vulnérabilité que l'on vient d'exploiter a été corrigée dans la version PyYAML 5.3.1.
Tapez les commandes suivantes pour mettre à jour la dépendance et mettre à jour le fichier requirements.txt. 
```
pip install pyyaml==5.3.1
.\update_requirements.py
```

7) Vérifier que le fichier "requirements.txt" s'est bien mis à jour et que la version de PyYAML est bien la 5.3.1 "PyYAML==5.3.1". On va maintenant vérifier que la vulnérabilité est bien corrigée. Relancer l'application.
9) Vérifier que le fichier "requirements.txt" s'est bien mis à jour et que la version de PyYAML est bien la 5.3.1 "PyYAML==5.3.1". On va maintenant vérifier que la vulnérabilité est bien corrigée. Relancer l'application.
```
.\application.py
```

8) Aller dans votre navigateur et dans la barre de navigation taper "127.0.0.1:5000". Essayer à nouveau d'envoyer le fichier YAML et regarder le terminal. Une erreur (500) devrait apparaître. Il n'est donc plus possible d'exploiter la vulnérabilité.
10) Aller dans votre navigateur et dans la barre de navigation taper "127.0.0.1:5000". Essayer à nouveau d'envoyer le fichier YAML et regarder le terminal. Une erreur (500) devrait apparaître. Il n'est donc plus possible d'exploiter la vulnérabilité.

9) Faire un git add / git commit / git push de l'application avec la nouvelle version de PyYAML vers la branch dev.
11) Faire un git add / git commit / git push de l'application avec la nouvelle version de PyYAML vers la branch dev.

10) Faire un merge de la branch dev vers la branch main
12) Faire un merge de la branch dev vers la branch main
```
git merge [branch]
```
# Help :
# Cheatsheet :
Supprimer tt les containers:
docker ps -aq | ForEach-Object { docker rm -f $_ } 
```
docker ps -aq | ForEach-Object { docker rm -f $_ }
```
Lister branch:
```
git branch
``` 
Changer de branch:
```
git checkout [branch]
```

____________________________________________________________________________________________________________
   ![HMP](https://github.com/user-attachments/assets/e7576c9a-c7bd-4150-aba2-9adee745a976)