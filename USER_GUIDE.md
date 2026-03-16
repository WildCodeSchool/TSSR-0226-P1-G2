*On doit avoir dans cette documentation :*
## Sommaire
- *Utilisation de base : comment utiliser les fonctionnalités clés*
- *Utilisation avancée : comment utiliser au mieux les options*
- [FAQ](#F-A-Q)

## Utilisation de PuTTY

### Fonctionnalités principales

Pour utiliser PuTTY et vous connecter au serveur Debian vous avez besoin de ces 6 options :

- 1 - Hostname or (Ip address) : indiquer ici le nom ou l'adresse IP de la mahcine dont on souhaite prendre le contrôle
- 2 - Port : Indiquer le port de cette même machine (par défaut Port SSH : 22)
- 3 - Connection type : sélectionner le type de connexion (par défaut SSH)
- 4 - Indiquer le nom de la session
- 5 - Charger une session 
- 6 - Sauvegarder une session

![lien à faire]()

**Configuration initiale :** Lors de la première connexion à une machine vous devez renseigner les point 1 à 3 puis indiquer en 4 le nom de la session lié à cette machine (veillez à être explicite concernant le nom de la session, par exemple en indiquant le nom d'utilisateur et le nom du serveur sur lequel la session permet la connexion). Il est primordial de bien sauvegarder ces éléments en cliquant sur "Save" (point 6) ce qui ajoutera les paramètres de session en dessous de "Default Settings"

**Chargement de paramètres de session :** Pour charger les paramètres d'une session il vous suffit de cliquer sur le nom de la session et de cliquer sur "Load" (point 5).

### Fonctionnalités complémentaires

**Enregistrement de Logs :**



**Modification de la police d'écriture :**

**Ajout d'un nom de machine au terminal :**

## FAQ

## FAQ-RDP
### Pourquoi ne puis-je pas me connecter à l’aide du Bureau à distance ?

Voici quelques solutions possibles aux problèmes courants que vous pouvez rencontrer lors de la tentative de connexion à un PC distant. Si ces solutions ne fonctionnent pas, vous trouverez plus d’aide sur le site web [Microsoft Community](https://answers.microsoft.com/).

- **Le PC distant est introuvable.** Vérifiez que vous disposez du bon nom du PC, puis vérifiez si vous avez entré ce nom correctement. Si vous ne pouvez toujours pas vous connecter, essayez d’utiliser l’adresse IP du PC distant au lieu du nom du PC.
    
- **Il y a un problème avec le réseau.** Vérifiez que vous disposez d’une connexion Internet.
    
- **Le port Bureau à distance peut être bloqué par un pare-feu.** Si vous utilisez le Pare-feu Windows, procédez comme suit :
  1. Ouvrez le Pare-feu Windows.
  2. Sélectionnez **Autoriser une application ou une fonctionnalité via le Pare-feu Windows**.
  3. Sélectionnez **Modifier les paramètres**. Vous pouvez être invité à fournir un mot de passe administrateur ou à confirmer votre choix.        
  4. Sous **applications et fonctionnalités autorisées**, sélectionnez Bureau à distance, puis appuyez ou sélectionnez **OK**.

        Si vous utilisez un autre pare-feu, vérifiez que le port du Bureau à distance (généralement 3389) est ouvert
- **Le PC distant peut autoriser uniquement les PC à se connecter avec l’authentification au niveau du réseau.**

- **Le PC distant peut être désactivé.** Vous ne pouvez pas vous connecter à un PC désactivé, endormi ou en veille prolongée. Assurez-vous que les paramètres de veille prolongée et de mise en veille prolongée sur le PC distant sont définis sur **Jamais** (la veille prolongée n’est pas disponible sur tous les PC.).

### Pourquoi ne puis-je pas trouver ou me connecter à mon PC ?

Vérifiez les éléments suivants :

- Le PC est-il allumé et éveillé ?
- Avez-vous entré le nom ou l’adresse IP approprié ?
- Le PC est-il sur un autre réseau ? Avez-vous configuré le PC pour permettre aux connexions externes via ?
- Vous vous connectez à une version de Windows prise en charge ?

### Pourquoi ne puis-je pas me connecter à un PC distant ?

Si vous pouvez voir l’écran de connexion du PC distant, mais que vous ne pouvez pas vous connecter, vous n’êtes peut-être pas ajouté au groupe Utilisateurs Bureau à distance ou à un groupe avec des droits d’administrateur sur le PC distant. Demandez à votre administrateur système de vous ajouter au groupe approprié.
### Quelles méthodes de connexion sont prises en charge pour les réseaux d’entreprise ?

Si vous souhaitez accéder à votre bureau office à partir de l’extérieur de votre réseau d’entreprise, votre entreprise doit vous fournir un moyen d’accès à distance. Le client Bureau à distance prend actuellement en charge les méthodes de connexion suivantes :

- Passerelle Terminal Server ou passerelle Bureau à distance
- Accès web Bureau à distance
- VPN (via les options VPN intégrées iOS)

### Comment utiliser tous mes moniteurs ?

Pour utiliser deux écrans ou plus, procédez comme suit :
1. Cliquez avec le bouton droit sur le Bureau à distance pour lequel vous souhaitez activer plusieurs écrans, puis sélectionnez **Modifier**.
2. Activez **Utiliser tous les moniteurs** et plein écran.

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
