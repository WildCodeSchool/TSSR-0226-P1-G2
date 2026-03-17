# TSSR-0226-P1-G2

## Sommaire
- [Présentation du projet](#Présentation-du-projet)
- [Membres du groupe par sprint](#Membres-du-groupe-par-sprint)
- [Choix techniques](#Choix-techniques)
- [Difficultés rencontrées](#Difficultés-rencontrées)
- [Solutions trouvées](#Solutions-trouvées)
- [Améliorations possibles](#Améliorations-possibles)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Présentation du projet
<span id="Présentation-du-projet"></span>
Le sujet choisi est la Téléassistance, il consiste à mettre en place une prise en main à distance d'un serveur depuis un client.

Plus précisément il s'agit de prendre contrôle :
- D'un serveur Debian depuis un client Windows et un client Linux
- D'un serveur Windows depuis un client Windows et un client Linux

La prise de contrôle se fait soit en GUI soit en CLI.

Objectif secondaire : Sécuriser l'accès et la connexion

![Schema synoptique Teleassitance](https://github.com/WildCodeSchool/TSSR-0226-P1-G2/blob/ebdabfdd3e4cd6aaccf40c897162ae2530993cb5/Ressources/Schema-synoptique-teleassistance.png)

## Membres du groupe par sprint
<span id="Présentation-du-projet"></span>
### Sprint 1

| Membres | Rôles      | Missions                                                                                                  |
| ------- | ---------- | --------------------------------------------------------------------------------------------------------- |
| Camille | PO         | Etudier la solution PuTTY et l'installer sur le client Windows, documenter INSTALL.md, Maquette README.ME |
| Saiah   | SM         | Etudier la solution VNC et l'installer sur le serveur Windows                                             |
| Aymeric | Technicien | Etudier la solution OpenSSH et l'installer sur le client Linux, documenter INSTALL.md                     |
| Patrick | Technicien | Etudier la solution RDP et l'installer sur le client Windows                                              |

### Sprint 2


| Membres | Rôles      | Missions |
| ------- | ---------- | -------- |
| Aymeric | PO         | Documenter INSTALL.md, documenter FAQ        |
| Patrick | SM         | Documenter INSTALL.md                        |
| Saiah   | Technicien | Documenter INSTALL.md, schéma synoptique     |
| Camille | Technicien | Documenter INSTALL.md, documenter FAQ        |



## Choix Techniques
<span id="Choix-techniques"></span>
### Clients


|                    | Windows       | Linux         |
| ------------------ | ------------- | ------------- |
| Nom                | WIN01         | UBU01         |
| OS                 | Windows 11    | Ubuntu 24 LTS |
| Compte utilisateur | Wilder        | wilder        |
| Mot de passe       | Azerty1*      | Azerty1*      |
| IP                 | 172.16.10.10  | 172.16.10.20  |
| Masque             | 255.255.255.0 | 255.255.255.0 |

### Serveurs

|                    | Windows                 | Linux         |
| ------------------ | ----------------------- | ------------- |
| Nom                | SRVWIN01                | SRVLX01       |
| OS                 | Windows Server 2025 GUI | Debian 13 CLI |
| Compte utilisateur | Wilder                  | wilder        |
| Mot de passe       | Azerty1*                | Azerty1*      |
| IP                 | 172.16.10.5             | 172.16.10.6   |
| Masque             | 255.255.255.0           | 255.255.255.0 |

### Logiciels

- Client Windows :
    - RDP / PuTTY
- Client Linux :
    - openSSH

- Serveur Windows :
    - VNC
- Serveur Debian :
    - openSSH


## Difficultés rencontrées
<span id="Difficultes-rencontrees"></span>

 - Se connecter avec le nom de la machine distante (au lieu de saisir l'adresse IP)
 - Lors de la prise de controle distante, les deux ecran basculent en fond noir.
 - La configuration des machines cliente et serveur a rencontré pas mal de problemes lors du Sprint 1, ce qui a ajoutté une pression supplementaire aux membres de l'équipe et décalé la realisations des objectifs mis en places.

## Solutions trouvées
<span id="Solutions-trouvees"></span>
 - Afin de garder l'environnement intact lors de la prise de contrôle décocher dans les option de configuration de TightVNC viewer  "cacher le papier-peint bureau".

## Améliorations possibles
<span id="Ameliorations-possibles"></span>

Une solution payante aura plus de possibilitées de configuration car elle se doit d'être a la pointe de ce qu'elle propose a ses clients.


