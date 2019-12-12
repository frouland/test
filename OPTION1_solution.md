<center><img src="images/jenkins.png" alt="Sonarqube" width="300"/></center>

# Utilisation du plugin "promoted builds"
But : utiliser le plugin "**promoted builds**" pour valider manuellement le déploiement sur le serveur de qualification

- Cible à atteindre :
<center><img src="images/jenkins5.png" alt="Jenkins" width="800"/></center>

- Installer le plugin "**promoted builds**"
<img src="images/option1_sol1.png" alt="Jenkins" width="1042"/>  

## Création de l'item Petclinic_promoteQualification
- Description : cet item doit permettre de stopper la chaine du build après la génération du package et obliger l'utilisateur à approuver manuellement le démarrage de la dernière étape du build.
- Nom : Petclinic_promoteQualification
- Type : Projet free-style
- Paramètre string : WORKSPACE\_PARENT
- Actions :
1. Prends en paramètre le workspace du build parent (WORKSPACE\_PARENT)  
<img src="images/jenkins1_sol8.png" alt="Jenkins" width="1042"/>
2. Activer l'option "**Promote builds when...**", spécifier un critère et une action
<img src="images/option1_sol2.png" alt="Jenkins" width="1042"/>
<img src="images/option1_sol3.png" alt="Jenkins" width="1042"/>
3. Modifier l'item "**Petclinic_package**" qui doit maintenant appeler ce nouvel item.
<img src="images/option1_sol4.png" alt="Jenkins" width="1042"/>
4. Lancer un build de l'item "**Petclinic\_compile**" manuellement
<img src="images/option1_sol5.png" alt="Jenkins" width="1042"/>
