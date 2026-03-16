# TSSR-0226-P1-G2

## Sommaire
- [Présentation du projet](#Présentation-du-projet)
- [Membres du groupe par sprint](#Membres-du-groupe-par-sprint)
- [Choix techniques](#Choix-techniques)
- [Difficultés rencontrées](#Difficultes-rencontrees)
- [Solutions trouvées](#Solutions-trouvees)
- [Améliorations possibles](#Ameliorations-possibles)


## Présentation du projet
<span id="Présentation-du-projet"></span>
Le sujet choisi est la Téléassistance, il consiste à mettre en place une prise en main à distance d'un serveur depuis un client.

Plus précisément il s'agit de prendre contrôle :
- D'un serveur Debian depuis un client Windows et un client Linux
- D'un serveur Windows depuis un client Windows et un client Linux

La prise de contrôle se fait soit en GUI soit en CLI.

Objectif secondaire : Sécuriser l'accès et la connexion

## Membres du groupe par sprint
<span id="Présentation-du-projet"></span>
### Sprint 1

| Membres | Rôles      | Missions                                                                                                  |
| ------- | ---------- | --------------------------------------------------------------------------------------------------------- |
| Camille | PO         | Etudier la solution PuTTY et l'installer sur le client Windows, documenter INSTALL.md, Maquette README.ME |
| Saiah   | SM         | Etudier la solution VNC et l'installer sur le serveur Windows                                             |
| Aymeric | Technicien | Etudier la solution OpenSSH et l'installer sur le client Linux, documenter INSTALL.md                     |
| Patrick | Technicien | Etudier la solution RDP et l'installer sur le client Windows                                             |

### Sprint 2


| Membres | Rôles      | Missions |
| ------- | ---------- | -------- |
| Aymeric | PO         | Documenter INSTALL.md, documenter FAQ         |
| Patrick | SM         | Documenter INSTALL.md        |
| Saiah   | Technicien | Documenter INSTALL.md         |
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


## Solutions trouvées
<span id="Solution-trouvees"></span>


## Améliorations possibles
<span id="Amelioration-possibles"></span>



