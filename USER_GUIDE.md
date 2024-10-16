# **GUIDE D UTILISATION NMAP**

## **SOMMAIRE**

### 1. [Présentation du Logiciel Nmap](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#1-pr%C3%A9sentation-du-logiciel-nmap-1)

### 2. [Utilisation basique (Ubuntu)](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#2-utilisation-basique-ubuntu-1)

### 3. [Utilisation avancée](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#3--utilisation-avanc%C3%A9e-certaines-commandes-peuvent-n%C3%A9cessit%C3%A9-dutiliser-sudo)
    
### 4. [Exemple et interprétation du résultat](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#4--exemple-et-interpr%C3%A9tation-du-r%C3%A9sultat)

### 5.  [Sources et avertissements](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#5--sources-et-avertissements-1)
    
---

### 1. Présentation du Logiciel Nmap

Nmap est un outil essentiel pour la reconnaissance de réseau et les audits de sécurité. Lancé en 1997, il s’est rapidement imposé comme l’un des outils de cybersécurité les plus fondamentaux et utilisés aujourd'hui. À l'origine conçu comme un scanner de ports avancé, Nmap a évolué pour devenir un outil multifonctionnel, offrant une large gamme d’applications, telles que la détection de mots de passe faibles, le scan d'adresses IPv6, la géolocalisation d'adresses IP et l’identification de vulnérabilités.

En tant qu’outil open source, Nmap est un atout précieux pour les professionnels de la sécurité, les équipes de mise en réseau, les administrateurs systèmes et d'autres spécialistes de l'informatique. Il permet d'analyser divers environnements, y compris des hôtes, des réseaux, des applications, des ordinateurs centraux, des systèmes Unix et Windows, ainsi que des systèmes de contrôle et d’acquisition de données, et des systèmes de contrôle industriel.

* source: https://www.lemagit.fr/conseil/Reseau-comment-scanner-les-ports-ouverts-en-utilisant-Nmap
  
---

### 2. Utilisation basique (Ubuntu)

Ces commandes fondamentales vous permettront de réaliser des scans initiaux, d'identifier les ports ouverts et de découvrir les services qui s'exécutent sur eux. Vous trouverez également les commandes donnant accés au manuel et à l'aide de Nmap.

#### - Accés aide et Manuel:
  * Manuel d'utilisation:
    
>    ` man nmap `
  * Aide pour les options:
    
>   `nmap --help`

#### - Commandes de base:

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

Nmap offre également la possibilité d'obtenir des informations approfondies sur les dispositifs connectés. Ci-dessous, vous trouverez quelques exemples de commandes qui permettent de réaliser une analyse plus pointue d'un hôte

* Scan de Détection d'OS: tente d'identifier l'OS de l'hôte
  
>`nmap -O [adresse ip cible]`

* Scan agressif: scan complet incluant la détection des services, des versions et des systèmes

> `nmap -A [adresse ip cible]`

* Scan TCP connect: Etablit une connexion complète avec le port

> `nmap sT [adresse ip cible]`

* Scan tous les ports UDP

> `nmap -sU [adresse ip cible]`

---

### 4.  Exemple et interprétation du résultat

> ![capture cmd basique](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/8a152d6a65d29c57d7f1cd25c362bfda508c19d1/capture/Capture%20d'%C3%A9cran%202024-10-16%20123035.png)

- **Ligne 1** : Sur la ligne 1, nous voyons que l'utilisateur "wilder", depuis le client CLILIN01, lance une commande `nmap` vers un serveur ayant pour adresse IP `[172.16.10.10]`.
- **Ligne 2** : La ligne 2 indique le lancement du logiciel nmap, en précisant l'heure et la date.
- **Ligne 3** : Ici, il est annoncé que nous allons recevoir un rapport de scan des ports de l'adresse IP scannée.
- **Ligne 4** : Cette ligne fournit des informations concernant le délai de réponse du serveur (latence).
- **Ligne 5** : Cette ligne indique le nombre de ports fermés.
- **Lignes 6 à 10** : Ici, nous avons le détail des ports ouverts et des services associés à chacun d'eux.
- **Ligne 12** : Enfin, cette ligne nous informe que l'hôte a bien été scanné en 5,03 secondes.

---

### 5.  Sources et avertissements

* Sources:
  
  * Définition: https://www.lemagit.fr/conseil/Reseau-comment-scanner-les-ports-ouverts-en-utilisant-Nmap
  * Site propriétaire: https://nmap.org/

* Avertissements:

Nous avons répertorié quelques commandes utiles pour notre projet. Si vous souhaitez en savoir plus, nous vous invitons à consulter le site de l'éditeur.

Nous déclinons toute responsabilité en cas de mauvaise utilisation de ces commandes. Ce projet a été réalisé dans le cadre d'une formation et n'a pas pour vocation de se substituer aux consignes de l'éditeur.



