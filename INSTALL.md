- *Prérequis techniques* :
  
- *Installation/Mise en place de la solution (explication étape par étape, ligne de code, copie d’écran, etc.) sur le client et/ou le serveur*
  - Installation Putty
  - Installation OPENSSH
  - Installation de TightVNC client et Serveur
  - Installation RDP
 
- *FAQ* :
  - Putty
  - OpenSSH
  - TightVNC Client / Serveur
  - RDP 
____

## Installation PuTTY

**Prérequis techniques :**
- Système d'exploitation Windows 64 bits
- *Une version pour système 32 bits est à disposition sur le site internet*

Vous pouvez télécharger la dernière version de PuTTY directement depuis le [Miscrosoft Store](https://apps.microsoft.com/detail/xpfnzksklbp7rj?hl=fr-FR&gl=FR) ou télécharger l'installeur depuis [le site officiel de Putty](https://putty.org/index.html)

____

Si vous utilisez Microsoft Store vous pouvez suivre l'installation à partir de l'étape 3, sinon voici la procédure :

**1** -  Sur la page d'accueil cliquer sur "Download PuTTY"

![Lien d'installation PuTTY - page d'accueil](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Lien-installation-Putty-page-accueil.png)

**2** -  Dans la rubrique "Package Files" cliquer sur le premier lien "putty-64bit-0.83-installer.msi" afin de télécharger l'installeur 

![Lin d'installation PuTTY - sélection intalleur](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Lien-installation-Putty-selection-installateur.png)

**3** -  Lancer l'installation en double-cliquant sur le fichier téléchargé, cliquer sur "Next" sur la première page

![Installeur PuTTY page 1](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page1.png)

**4** -  Sélectionner le chemin d'installation du logiciel (Ne modifier qu'en cas d'installation particulière)

![Installeur PuTTY - Sélection chemin d'installation](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page2-Emplacement-installation.png)

**5** -  Pour ajouter un raccourci sur le bureau, dans la page "Product Features" cliquer sur le second titre "Add shortcut to PuTTY on the desktop" et sélectionner "Will be installed on local hard drive"

![Installeur PuTTY - Product Features](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page3-choix-options.png)

**6** -  Cliquer sur "Yes" afin d'accepter l'installation du logiciel

![Installeur PuTTY - Accord admin](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page4-validation-admin.png)

**7** -  Cliquer sur "Finish" afin de terminer l'installation, penser à décocher "view Readme File" pour ne pas déclencher l'ouverture du manuel d'utilisation - si non souhaité

![Installeur PuTTY - Finish](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/d76e592fa359ff8d816e8174c2dd8c7628554d21/Ressources/Installeur-Putty-page5-fin-readme.png)

###FAQ - PuTTY

____

## Installation OPENSSH

**Prérequis techniques :**
  - Bénéficier des droits Administrateur

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
## FAQ - OpenSSH




____



## Installation TightVNC


| Prérequis technique pour windows server 2025                                                                                                                                                                                                                                                                                                                                                                                                                                             | Prérequis technique minimum pour Ubuntu LTS 24.04                                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **CPU Minimum**:<br>    - Processeur 1,4 GHz 64 bits<br>    - Compatible avec le jeu d’instructions x64<br><br>**RAM Minimum :**<br>    - 2 Go pour Server Core<br>    - 2 Go pour Serveur avec interface de bureau, 4 Go recommandés<br><br>**Stockage Minimum :**<br>    - 32 Go d’espace<br><br>**Réseau Minimum :** <br>    - Adaptateur Ethernet pouvant atteindre un débit d’au moins 1 gigaoctet par seconde.<br>    - Conforme à la spécification de l’architecture PCI Express. | **CPU Minimum :**<br>	 - Processeur 2 GHz double cœur ou plus ;<br><br> **RAM Minimum :** <br>	- 4 Go de mémoire vive (8 Go recommandés) ;<br><br>**Stockage minimum :**<br>	 - 25 Go d'espace disque disponible<br>	 <br> **Carte graphique :**<br>    - Carte graphique compatible avec une résolution 1024×768 minimum ;<br>	<br>**Connectique :**<br>	- Clé USB de 8 Go pour l'installation.<br>    - Une souris (ou touchpad sur PC) |

____

## Installation de TightVNC JavaViewer sur Ubuntu

**1**. Vérifier que nous avons java via le terminal

```bash
java -version
```

**2**. Installation de Java s'il n'est pas présent 

```bash 
sudo apt install openjdk-25-jre
```

**3**. Vérification de la présence de Java à nouveau

```bash
java -version
```

**4**. Je me rend sur le site de TightVNC pour telecharger le client VNC qui est le suivant : TightVNC Java Viewer

![sitedinstall](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/main/Ressources/Install-TightVNC-linux-4.png)

**5**. Une fois telechargé, je vais dans le dossier Téléchargement pour vérifier que le fichier Zip est bien présent puis je le décompresse via le terminal

```bash
cd ~/Téléchargements
```
```bash
ls
```
```bash
unzip "NomDuFichierZip"
```

**6**. Le logiciel est installé et prêt a l'emploi


____


## Installation de TightVNC server sur Windows server 2025

**1**. Aller sur le site de TightVNC et télécharger l'application : Installer for windows -64bits

![[Pasted image 20260316120706.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%201.png)

**2**. Lancer l'executable et commencer l'installation de TightVNC server

![[Pasted image 20260316120750.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%202.png)

**3**. Accepter les thermes de la license *

![[Pasted image 20260316120822.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%203.png)

**4**. Choisir le setup "custom" et ne selectionner que TightVNC server

![[Pasted image 20260316120851.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%204.png)
![[Pasted image 20260316120925.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%205.png)

**5**. Pret a etre installé et on lance l'install 

![[Pasted image 20260316121015.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%206.png)

**6**. Definir un mot de passe pour sécuriser le lance et l'autorisation de controle a distance

![[Pasted image 20260316121106.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%207.png)

**7**. L'installation est complete 

![[Pasted image 20260316121153.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%208.png)

**8**. Verification du lancement du serveur avec demande d'authentification

![[Pasted image 20260316121234.png]](https://raw.githubusercontent.com/WildCodeSchool/TSSR-0226-P1-G2/6607b2922d092a8b9d6db3af30fcd7e9fba8dccb/Ressources/Install%20TightVNC%20windows%20server%202025%209.png)


## FAQ - TightVNC



____



## Installation RDP

**Prérequis techniques :**
		- RDP est intégré sur Windows 11 et Windows Server 2022-2025

____

**1** - Accéder au client RDP : 
		- Depuis le clavier, appuyez sur les touches Win + R
		- Saisissez **mstsc** ou bien, dans le menu démarrer, recherchez « **Connexion Bureau à Distance** »


| ![Ouvrir via tableur](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/main/Ressources/mstsc.png) | ![Ouvrir via recherche](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/main/Ressources/Ouvrir_l_appli.png) |
| ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |



**2** - Utilisation :
		- Saisissez l’adresse IP ou le nom de la machine distante
		- Cliquez sur connexions
		- Saisissez les identifiants utilisateur (nom utilisateur & mot de passe)
		- Cliquez sur Ok pour établir la connexion

![Entrer ladresse IP](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/main/Ressources/RDP.png)

**3** - Configuration du PC pour Accepter les Connexions RDP 
Pour recevoir les connexions RDP sur son ordinateur. Il faut activer le Bureau à Distance :
		- Accédez aux paramètres Windows en appuyant sur les touches **Win + I**.
	    - Allez dans **Système** puis **Bureau à distance**.
	    - Activez l’option **Bureau à distance**.
