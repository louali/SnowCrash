On a encore deux fichiers: un binaire et un fichier token pour lequel nous n'avons aucune permission.

On essaye de donner token en paramètre:

![image](./token.png)

On ne peut pas y accéder, on essaye donc de lui donner un fichier vide:

![image](./empty_coucou.png)

Ça fonctionne mais rien ne se passe, on essaye ensuite de donner un fichier rempli:

![image](./coucou.png)

Le script retourne le contenu du fichier.

En lançant la commande strings sur level08 on trouve:

![image](./strings.png)

On imagine que le binaire renvoie `You may not access '%s'` quand le fichier a pour nom token. Pour prouver ça on créé un nouveau fichier token:

![image](./created_token.png)

Pour accéder au contenu il faudrait donc changer le nom de token.
En faisant `chmod 777 .` on peut se donner tous les droits dans le répertoire courant et donc changer le nom de token:

![image](./password.png)

On peut utiliser ce mot de passe pour accéder à l'utilisateur flag08 et trouver le flag.