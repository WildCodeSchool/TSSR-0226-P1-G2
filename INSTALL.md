*On doit avoir dans cette documentation (pour la tâche principale et secondaire) :*
- *Prérequis techniques*
- *Installation/Mise en place de la solution (explication étape par étape, ligne de code, copie d’écran, etc.) sur le client et/ou le serveur*
  - Installation OPENSSH
- *FAQ*
____

## Installation PuTTY

**Prérequis techniques :**
- Système d'exploitation Windows 64 bits
- *Une version pour système 32 bits est à disposition sur le site internet*

Vous pouvez télécharger la dernière version de PuTTY directement depuis le [Miscrosoft Store](https://apps.microsoft.com/detail/xpfnzksklbp7rj?hl=fr-FR&gl=FR) ou télécharger l'installeur depuis [le site officiel de Putty](https://putty.org/index.html)

Si vous utilisez Microsoft Store vous pouvez suivre l'installation à partir de l'étape 3, sinon voici la procédure :

**1** -  Sur la page d'accueil cliquer sur "Download PuTTY"

[Lien d'installation PuTTY - page d'accueil](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Lien-installation-Putty-page-accueil.png)

**2** -  Dans la rubrique "Package Files" cliquer sur le premier lien "putty-64bit-0.83-installer.msi" afin de télécharger l'installeur 

[Lin d'installation PuTTY - sélection intalleur](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Lien-installation-Putty-selection-installateur.png)

**3** -  Lancer l'installation en double-cliquant sur le fichier téléchargé, cliquer sur "Next" sur la première page

[Installeur PuTTY page 1](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page1.png)

**4** -  Sélectionner le chemin d'installation du logiciel (Ne modifier qu'en cas d'installation particulière)

[Installeur PuTTY - Sélection chemin d'installation](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page2-Emplacement-installation.png)

**5** -  Pour ajouter un raccourci sur le bureau, dans la page "Product Features" cliquer sur le second titre "Add shortcut to PuTTY on the desktop" et sélectionner "Will be installed on local hard drive"

[Installeur PuTTY - Product Features](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page3-choix-options.png)

**6** -  Cliquer sur "Yes" afin d'accepter l'installation du logiciel

[Installeur PuTTY - Accord admin](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page4-validation-admin.png)

**7** -  Cliquer sur "Finish" afin de terminer l'installation, penser à décocher "view Readme File" pour ne pas déclencher l'ouverture du manuel d'utilisation - si non souhaité

[Installeur PuTTY - Finish](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page5-fin-readme.png)

###FAQ - PuTTY

## Installation OPENSSH
**1** -  Lancer la commande suivante pour installer <u>OpenSSH</u> sur le serveur

``` bash
sudo apt install openssh-server -y
```

**2** -  Activer le SSH immédiatement ainsi qu'au démarrage

``` bash
sudo systemctl enable ssh --now
```

**3** -  Vérifier le statut du SSH

``` bash
sudo systemctl status ssh --no-pager
```

**4** - Lecture du Statut : *Active running* (ou *enabled*) en <font color="#00b050">vert</font> indique que le daemon OpenSSH est bien actif dans le système

![_Active_running_ou_enabled_en_vert_indique_que_le_daemon_OpenBSD_Secure_Shell_server_est_bien_actif_dans_le_systeme](Ressources/4th_-_Active_running_ou_enabled_en_vert_indique_que_le_daemon_OpenBSD_Secure_Shell_server_est_bien_actif_dans_le_systeme..png)

**Optionnel 1** - Si un pare-feu UFW est utilisé, entrer cette Commande pour autoriser SSH

``` bash
sudo ufw allow OpenSSH
```

**Optionnel 2** - Test côté Serveur s'il écoute sur le *port 22*

``` bash
ss -tnlp | grep :22
```

# Création d'une clé SSH

**1** - Entrer la commande suivante puis choisir le dossier de destination de la clé (en rouge le <font color="#ff0000">champ d'écriture</font> / en vert le <font color="#00b050">chemin par défaut</font> si aucune donnée n'est entrée)

``` bash
ssh-keygen -t ed25519 -a 100 -C "NomDuPosteClient"
```

![Trouver le bon chemin](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/2531796e2535b3c6adc28f1986d19019920709b7/Ressources/Choisir%20le%20dossier%20de%20destination%20de%20la%20cl%C3%A9.png) 

**2** - Choisir le **PassPhrase** qui viendra protéger la clé SSH

**3** - Entrer à nouveau le **PassPhrase** pour valider la création de la clé SSH

**4** - Copiez automatiquement votre clé publique vers le serveur avec ssh-copy-id

``` bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub utilisateur@ip_ou_domaine
```
