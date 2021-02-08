En faisant un cat de level04.pl on remarque deux choses:

![image info](./cat_level04.png)

On essaye donc d'accéder à localhost:4747 avec le paramètre x à 1:

![image info](./curl_level04.png)

Le script renvoi le résultat de l'appel à la commande system echo.

Les backquotes permettent en perl d'éxécuter des commandes systèmes.

On essaye la même chose en appelant getflag:

![image info](./getflag.png)
