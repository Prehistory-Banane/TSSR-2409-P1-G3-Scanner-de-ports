# **USER GUIDE NMAP**

## **SOMMAIRE**

### 1. [Présentation du Logiciel Nmap](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#1-pr%C3%A9sentation-du-logiciel-nmap-1)

### 2. [Utilisation basique (Ubuntu)](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#2-utilisation-basique-ubuntu-1)

### 3. [Utilisation avancée](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#3--utilisation-avanc%C3%A9e)
    
### 4. FAQ : solutions aux problèmes connus et communs liés à l’installation et à la configuration
    
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

#### - Les commandes simple (sans `sudo`):


* Scan des 1000 ports les plus utilisés de l'ip cible

> `nmap [adresse ip cible]`

* Scan des ports d'un sous réseau

> `nmap [adresse ip cible]/24`

* Scan des 100 ports les plus utilisés de l'ip cible

> `nmap -F [adresse ip cible]`

* Scan de tous les ports les plus utilisés de l'ip cible

> `nmap -P- [adresse ip cible]`

* Scan d'un seul port

> `nmap -P {port} [adresse ip cible]`



#### - Interpréter le résultat (exemple):
![capture cmd basique](capture/Capture d'écran 2024-10-16 123035.png)
=> a definir

---

### 3.  Utilisation avancée

intro ici:

*
*
*
---

### 4.  FAQ : solutions aux problèmes connus et communs liés à l’utilisation

ici

*
*
*
