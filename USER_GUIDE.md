*On doit avoir dans cette documentation :*
## Sommaire
- *Utilisation de base : comment utiliser les fonctionnalités clés*
- *Utilisation avancée : comment utiliser au mieux les options*
- [FAQ](#F-A-Q)

## FAQ

## FAQ-VNC
### Quelles versions de Windows TightVNC supporte-t-il ?

TightVNC fonctionne quasiment sur n’importe quelle version de Windows (les systèmes 32 et 64 bits sont pris en charge) :

- Windows XP / Vista / 7 / 8 / 8.1 / 10 / 11,
- versions correspondantes de Windows Server.
Sur Windows XP, vous devriez avoir le dernier Service Pack installé. Les systèmes Windows CE ne le sont pas soutenu.
## Quelle est la Configuration requise pour utiliser TightVNC

Il n’y a pas d’espace disque, ni de RAM minimum . TightVNC utilise si peu d’espace et de mémoire qu’il peut tourner partout où Windows fonctionne.
## Comment désinstaller TightVNC ?

Normalement, TightVNC peut être retiré comme n’importe quel autre logiciel, depuis le panneau de configuration (Ajouter/Supprimer des programmes). Mais si quelque chose tourne mal, ou si TightVNC a été installé manuellement, vous Vous pouvez toujours le retirer manuellement en utilisant les procédures étape par étape ci-dessous : 
1. Connectez-vous en tant qu’administrateur (ou en tant qu’utilisateur avec des permissions similaires).
2. Si le serveur TightVNC tourne, fermez-le. Si l’icône du plateau tourne mais ne s’affiche pas, Choisissez Gestion des processus, localisez tous les processus tvnserver.exe et fermez chacun d’eux.
3. Si TightVNC Server était enregistré comme service système, désenregistrez-le. Pour cela, localisez tvnserver.exe fichier sous \Program Files\TightVNC (ou là où TightVNC était installé), et Tapez dans la ligne de commande : tvnserver.exe -remove
4. Supprimez tout le dossier \Program Files\TightVNC (ou là où se trouvait TightVNC).
5. Supprimez tous les raccourcis TightVNC du menu Démarrer.
6. Supprimez les paramètres du registre si vous le souhaitez. Les réglages se trouvent dans HKEY_LOCAL_MACHINE\Logiciel\TightVNC et/ou HKEY_CURRENT_USER\Logiciel\TightVNC

## FAQ-OPENSSH
### Quels systèmes d’exploitation sont pris en charge ?

Un aperçu rapide des autres systèmes d’exploitation pris en charge est ci-dessous.
 OpenBSD  NetBSD, FreeBSD, AIX,HP-UX, IRIX, Linux, NeXT, SCO, SNI/Unix Reliant, Solaris, Digital Unix/Tru64/OSF, MacOS X

Liste des fournisseurs qui incluent OpenSSH dans leurs distributions : [www.openssh.com/users.html](http://heap.altlinux.org/usr/share/doc/openssh-3.6.1p2/users.html)

### Pourquoi SSH 2.3 a-t-il des problèmes d’interopérabilité avec OpenSSH 2.1.1 ?

SSH 2.3 et les versions antérieures contiennent une faille dans leur implémentation HMAC. Leur code ne fournissait pas la sortie complète du bloc de données du digest, et il fournissait toujours 128 bits. Pour des digestions plus longues, cela empêchait SSH 2.3 d'interopérer avec OpenSSH.

OpenSSH 2.2.0 détecte que SSH 2.3 présente ce défaut. Les Prochaines Versions vont corriger ce bug. Ou vous pouvez ajouter ce qui suit à SSH 2.3 _sshd2_config_.
``Mac hmac-md5``

### SFTP/SCP échoue à la connexion, mais le SSH est correct.

SFTP et/ou SCP peuvent tomber en panne à la connexion si vous avez une initialisation de shell (.profile, .bashrc, .cshrc, etc.) qui produit une sortie pour les sessions non interactives. Cette sortie embrouille le client sftp/scp. Vous pouvez vérifier si cela se produit en exécutant :
``ssh yourhost /usr/bin/true``
Si la commande ci-dessus produit une quelconque sortie, alors vous devez modifier votre initialisation du shell.
### Pourquoi OpenSSH affiche-t-il : erreur du protocole de dispatch : type 20

Des problèmes d’interopération ont été observés par les anciennes versions de OpenSSH ne supportant pas la reprogrammation de session. Cependant, le SSH 2.3 commercial essayait d'activer cette fonctionnalité, et vous pouviez constater que la connexion se fige ou voir le message d’erreur « **Erreur de protocole de dispatch : Type 20** ". Pour résoudre ce problème, soit il faut passer à une version récente d’OpenSSH ou désactivez la reprogrammation en ajoutant ce qui suit à la _ssh2_config_ ou _sshd2_config_ de votre SSH 2.3 commercial.
``RekeyIntervalSeconds 0``
