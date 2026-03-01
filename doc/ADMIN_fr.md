L'URL de l'interface admin est <https://__DOMAIN____PATH__admin>. Seuls les utilisateurs du groupe __admins__ peuvent y accéder.  
L'adresse de l'API est <https://__DOMAIN____PATH__>.  



### Identifiants

:key: Un utilisateur admin __ADMIN__ est créé avec les clés suivantes  :  
`AWS_ACCESS_KEY_ID=__ADMIN_KEY__`   
`AWS_SECRET_ACCESS_KEY=__ADMIN_SECRET__`  

D'autres utilisateurs peuvent être ajoutés via le panel admin de seaweedfs.

### Répertoires de données et pod `Volumes`
Le répertoire de données du premier pod volume est situé dans `/home/yunohost.app/seaweedfs/datadir`.  
D'autres répertoires peuvent être ajoutés via le panneau de configuration en créant de nouveaux pods volumes.  

###  Création des buckets  
Les buckets peuvent être créés en `path_style` ou `virtual_host`.  
En `virtual_host`:  
* il faut ajouter un domaine nommé `<bucket_name>.__DOMAIN__`
* il faut ensuite installer l'app [Redirect App](https://apps.yunohost.org/app/redirect) (`redirect_ynh`) à la racine de ce domaine et la faire pointer en mode `reverse_proxy` sur `http://127.0.0.1:__PORT_API__ `
___
### Exemples d'utilisation
#### Restic
* Installer l'app restic et choisir comme dépôt pour les sauvegardes `s3:https://__DOMAIN__/<bucket_name>`.
* En ligne de commande, ouvrir le shell restic:  `yunohost app shell restic`
* Initialiser le dépôt : `./restic -r s3:https://__DOMAIN__/<bucket_name> init` then exit.
* Démarrer la sauvegarde via la webadmin ou en ligne de commande.
#### Backrest
#### Nextcloud
Paramètres d'administration > Stockage externe > Stockage S3 > Clé d'accès.  
* nom du bucket
* endpoint URL : https://__DOMAIN__
* cocher `Active pathstyle`
* Key id : `__ADMIN_KEY__`
* Secret key: `__ADMIN_SECRET__`
#### Peertube
* éditer `var/www/peertube/config/production.yaml:
```
object_storage:
  enabled: true
``
