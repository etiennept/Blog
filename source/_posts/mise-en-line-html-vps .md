---
title: Mise en ligne  ficher html sur un vps linux 
resume:  Comment mettre en line un fichier html sur un vps linux. Description étape part étape  
---


La mise en ligne d'un ficher html sur un vps linux parait compliqué mais cela est simple. 
  
On commence par se connecter au serveur via le ssh.
Puis sur le serveur on installe [nginx]( https://nginx.org/en/ ) si on ne l'a déja fait. 

Ensuite on ouvre sur le terminal le ficher suivant : /etc/nginx/sites-avaibles/nginx.conf.


```  
   server{
   ...
        listen 80
        ...
        server_name example.com 
        ... 
        root : /var/www/dir_name        
        ... 
        index : file_name 
        ...  
   }
```

où 
- 80 :  port d'envoi ici le port http   
- exemple.com:  le nom de domaine du site 
- /var/www/dir_name  : le chemin du dossier ou se trouve le ficher html  
- file_name : le nom du fich.er html   

Quand tout est bien parametré  on execute cette commande : 

```shell
    sudo service nginx restart
```


Puis on lance cette comande sur l'ordinateur.

```shell 
    scp file_name  username@vps_host:/var/www/dir_name 
```

ou 
- file_name : le nom du fichier    
- username : l
- vps_host : l'addresse internet du vps  
- /var/www/dir_name  : le chemin du dossier ou se trouve le ficher html  