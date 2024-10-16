# **USER GUIDE NMAP**

## **SOMMAIRE**

### 1. [Présentation du Logiciel Nmap](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#1-pr%C3%A9sentation-du-logiciel-nmap-1)

### 2. [Utilisation basique (Ubuntu)](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#2-utilisation-basique-ubuntu-1)

### 3. [Utilisation avancée](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#3--utilisation-avanc%C3%A9e)
    
### 4. [Interpréter le résultat (exemple)]()
    
---

### 1. Présentation du Logiciel Nmap

Nmap est un outil qui permet de faire une reconnaissance du réseau et des audits de sécurité. Sorti en 1997, il est l’un des outils de cybersécurité les plus basiques et les plus utilisés aujourd’hui. Depuis ses débuts en tant que scanner de port avancé, il a évolué en un outil multifonctionnel, avec une panoplie de cas d’usage pour découvrir des mots de passe faibles, scanner des adresses IPv6, effectuer la géolocalisation d’adresses IP, détecter des vulnérabilités et plus encore.

Cet outil open source aide les professionnels de la sécurité, les équipes de mise en réseau, les administrateurs système et autres personnels informatiques à analyser les hôtes, les réseaux, les applications, les ordinateurs centraux, les environnements Unix et Windows, les systèmes de contrôle et d’acquisition de données et les systèmes de contrôle industriel.

* source: https://www.lemagit.fr/conseil/Reseau-comment-scanner-les-ports-ouverts-en-utilisant-Nmap
  
---

### 2. Utilisation basique (Ubuntu)

#### - Accés aide et Manuel:
  * Manuel d'utilisation:
    
>    ` man nmap `
  * Aide pour les options:
    
>   `nmap --help`

#### - Les commandes simple:


* Scan des 1000 ports les plus utilisés de l'ip cible

> `nmap [adresse ip cible]`

* Scan des ports d'un sous réseau

> `nmap [adresse ip cible]/24`

* Scan des 100 ports les plus utilisés de l'ip cible

> `nmap -F [adresse ip cible]`

* Scan de tous les ports les plus utilisés de l'ip cible

> `nmap -P 1-65535 [adresse ip cible]`

* Scan d'un seul port

> `nmap -P {port} [adresse ip cible]`

---

### 3.  Utilisation avancée: certaines commandes peuvent nécessité d'utiliser `sudo`

intro ici:

* Scan de Détection d'OS: tente d'identifier l'OS de l'hôte
  
>`nmap -O [adresse ip cible]`

* Scan agressif: scan complet incluant la détection des services, des versions et des systèmes

> `nmap -A [adresse ip cible]`

* Scan TCP connect: Etablit une connexion complète avec le port

> `nmap sT [adresse ip cible]`

* Scan tous les ports UDP

> `nmap -sU [adresse ip cible]`

---

### 4.  Interpréter le résultat (exemple)

![capture cmd basique](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/8a152d6a65d29c57d7f1cd25c362bfda508c19d1/capture/Capture%20d'%C3%A9cran%202024-10-16%20123035.png)

- **Ligne 1**: Sur la ligne 1 nous voyons que l'utilisateur wilder depuis le client CLILIN01 lance une commande `nmap` vers un serveur ayant comme adresse ip `[172.16.10.10]`;
- **Ligne 2**: La ligne 2 nous annonce le lancement du logiciel nmap en précisant l'heure et la date;
- **Ligne 3**: Ici on nous annonce que l'on va recevoir un scan report des ports de l'adresse ip scanné;
- **Ligne 4**: Nous avons ici l'information concernant le délais de réponse du serveur (latence);
- **Ligne 5**: Cette ligne nous indique combien de ports sont fermés
- **Ligne 6 à 10**: Ici nous avons en détails qu'elle port sont ouvert et le service lié à chaque port ouvert;
- **Ligne 12**: Et enfin cette ligne nous indique que l'hôte a bien été scanné en 5.03 seconds.
  
---

### 5.  FAQ : solutions aux problèmes connus et communs liés à l’utilisation

ici

*
*
*
