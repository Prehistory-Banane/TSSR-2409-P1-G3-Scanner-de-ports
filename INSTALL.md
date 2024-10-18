# **DOCUMENTATION ADMINISTRATEUR**

## **SOMMAIRE**

### :one: [Prérequis techniques](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/INSTALL.md#one-pr%C3%A9requis-techniques-1)

### :two: [Étapes d'installation et de conf. : instruction étape par étape](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/INSTALL.md#two--%C3%A9tapes-dinstallation-et-de-conf--instruction-%C3%A9tape-par-%C3%A9tape)
    
### :three: [Solutions aux problèmes connus et communs liés à l’installation et à la configuration](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/INSTALL.md#three--solutions-aux-probl%C3%A8mes-connus-et-communs-li%C3%A9s-%C3%A0-linstallation-et-%C3%A0-la-configuration) 
    
---

### :one: Prérequis techniques

Pour pouvoir envisager le scan de port, il est nécessaire de remplir certaines conditions. Notamment se trouver dans un environnement qui comporte au moins une machine serveur et une machine client, les deux communiquant par le biais d'une connexion à un même réseau.

* Une machine serveur :  
    - Définition d'une machine serveur :  
        - C'est un ordinateur ou un dispositif dédié dans un réseau informatique souvent doté de ressources matérielles optimisées (puissance de calcul, mémoire, stockage) pour gérer de nombreuses connexions et requêtes simultanées.  
        - Un serveur est configuré pour fournir des services, des ressources ou des données à d'autres ordinateurs appelés clients. Le serveur gère les requêtes des clients et leur renvoie les réponses appropriées selon le type de service offert. Ces services peuvent inclure, mais ne sont pas limités à, l'hébergement de fichiers, le traitement de données, la gestion d'applications, la fourniture d'accès à des bases de données, etc.
        - Les protocoles réseau les plus utilisés dans les environnements serveurs incluent HTTP/HTTPS (serveurs web), FTP (serveurs de fichiers), SMTP (serveurs de messagerie), ou encore DNS et DHCP pour la gestion du réseau.
          
    - Caractéristiques principales d'une machine serveur :
        - Accessibilité : Un serveur est accessible aux clients via des adresses IP ou des noms de domaine.  
        - Fiabilité : Il est conçu pour fonctionner en continu, assurant une disponibilité maximale des services.  
        - Sécurité : Les serveurs sont souvent configurés avec des mesures de sécurité renforcées pour protéger les données et les ressources.  
        - Performance : Optimisé pour supporter des charges importantes en termes de traitement et de connexions simultanées.

    - Système d'exploitation :  
  Microsoft Windows Server, Linux Debian, UNIX, ou encore NetWare sont des exemples de systèmes d'exploitation utilisés dans le cadre d'une machine serveur.

    
* Une machine client :  
    - Définition d'une machine client :  
        - Une machine client est un ordinateur, un smartphone, un périphérique ou un système connecté à un réseau informatique qui envoie des requêtes à une machine serveur pour accéder à des services, des ressources ou des données. Le client initie la communication avec le serveur en fonction des besoins de l'utilisateur, tels que l'accès à des pages web, le téléchargement de fichiers, l'exécution d'applications distantes, ou la consultation d'une base de données.  
        - Le rôle d'une machine client est principalement de consommer les services offerts par les serveurs, que ce soit dans un modèle client-serveur traditionnel ou dans un environnement plus distribué comme le cloud computing.
          
    - Caractéristiques principales d'une machine client :
        - Initiation de la communication : Contrairement aux serveurs, les clients sont ceux qui lancent les requêtes en premier, qu'il s'agisse de demander des données, des ressources ou des services.
        - Dépendance : Les clients dépendent des serveurs pour accéder à des services ou des ressources. Sans serveur, un client ne peut pas obtenir les informations ou les fonctionnalités recherchées.
        - Interface utilisateur : Les clients incluent souvent des interfaces utilisateur (comme des navigateurs web, des logiciels de gestion de fichiers, ou des clients de messagerie) permettant à l'utilisateur d'interagir facilement avec le serveur.
    - Types de clients :
        - Client léger : Machine qui dépend fortement d'un serveur pour ses opérations (exemple : client RDS ou VDI).
        - Client lourd : Machine qui exécute localement une grande partie de ses traitements, mais s'appuie sur un serveur pour certaines tâches (exemple : un ordinateur avec un logiciel de gestion accédant à une base de données distante).

    - Système d'exploitation :  
  Microsoft Windows (principalement 10 et 11), macOS/iOS, GNU/Linux sont des exemples de systèmes d'exploitation utilisés dans le cadre d'une machine client.
 
* Un réseau
    - Définition d'un réseau :  
        - Un réseau est un ensemble d'ordinateurs, de périphériques ou de systèmes interconnectés qui communiquent entre eux pour partager des ressources et des services. Dans une configuration serveur/clients, le réseau est l'infrastructure qui permet la communication et le partage de services entre les clients et les serveurs. Il fournit un moyen pour les clients d'accéder aux ressources centralisées hébergées par les serveurs, tout en assurant la fiabilité, la sécurité, et l'efficacité des échanges.  
        - Un réseau permet la transmission de données sous forme de paquets à travers divers protocoles et technologies, tels que TCP/IP pour l'Internet ou Ethernet pour les réseaux locaux (LAN). Il peut être configuré localement (intranet) ou à plus grande échelle (internet), et il relie les clients aux serveurs via des adresses IP et des technologies réseau tant hardware (switches, routeurs), que software (firewalls).  
  
    - Caractéristiques d'un réseau :  
        - Centralisation des services : Les serveurs offrent des services et des ressources (fichiers, bases de données, applications, etc.) auxquels les clients accèdent via le réseau. Cela centralise la gestion et l'accès aux données.
        - Distribution des requêtes : Les clients initient des requêtes pour accéder aux services offerts par le(s) serveur(s). Le réseau gère la transmission des données entre les clients et les serveurs.
        - Partage des ressources : Un réseau permet aux clients de partager des fichiers, des imprimantes, des applications, des bases de données ou d'autres ressources informatiques hébergées sur le serveur.
        - Fiabilité et sécurité : Le réseau doit assurer une connectivité fiable, avec des mécanismes de sécurité pour protéger les échanges de données entre les clients et les serveurs (par exemple, en utilisant le cryptage, l'authentification ou des firewalls).  

    - Composants d'un réseau :  
        - Serveurs : Machines qui fournissent des services, comme des serveurs web, de fichiers, de bases de données ou d'applications.
        - Clients : Machines ou périphériques qui consomment des services (ordinateurs, smartphones, tablettes, etc.).
        - Protocoles : Règles de communication entre les clients et les serveurs (ex. : HTTP/HTTPS, FTP, SMB, DNS).
        - Commutateurs et routeurs : Équipements réseau qui acheminent le trafic entre les clients et les serveurs, en gérant les paquets de données.
        - Firewalls et sécurité réseau : Dispositifs et logiciels qui protègent les données et assurent la sécurité du réseau contre les intrusions ou les menaces.  
     
    - Types de réseaux :  
        - Réseau local (LAN) : Un réseau couvrant une zone géographique restreinte, comme un bureau ou une entreprise. Les clients et les serveurs sont souvent situés dans le même bâtiment.
        - Réseau étendu (WAN) : Un réseau qui couvre une grande zone géographique, comme l'interconnexion de plusieurs bureaux à distance. Internet est un exemple de WAN.
        - Intranet : Un réseau privé utilisé au sein d'une organisation, souvent pour permettre aux employés d'accéder à des ressources internes.
        - Cloud : De plus en plus, les réseaux clients/serveurs peuvent inclure des serveurs distants accessibles via Internet, appelés serveurs "cloud", qui hébergent des applications ou des données.



---

### :two:  Étapes d'installation et de conf. : instruction étape par étape

Parmi toutes les solutions existantes pour scanner des ports nous allons nous concentrer sur le logiciel Nmap, qui est à la fois accessible, fiable et efficace.
Vous pourrez trouver [une présentation de ce logiciel](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/README.md#4-nmap-cest-quoi-1) dans le document README.md.  
Vous trouverez ci-dessous les méthodes d'installation de NMap sur trois des systèmes d'exploitation les plus courants.  


### - Installation sur Windows

**1/ Télécharger Nmap sur le site officiel à l'adresse `https://nmap.org/download`**\
**2/ Lancer l'installation de Nmap**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows.png" width="1000">
</picture>\
\
\
**3/ Appuyer sur Next à chaque sans rien toucher aux options, puis cliquer sur Install**
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%202.png" width="500">
</picture>
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%203.png" width="500">
</picture>\
\
\
**4/ L'installateur enchaîne sur l'installation de Npcap, une bibliothèque nécessaire au bon fonctionnement de Nmap**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%204.png" width="500">
</picture>\
\
\
**5/ Valider toutes les étapes sans modifier les options**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%205.png" width="500">
</picture>
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%207.png" width="500">  
</picture>\
\
\
**7/ Choisir éventuellement si vous souhaiter créer des raccourcis ou non**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%209.png" width="500">
</picture>\
\
\
**8/ Nmap est installé**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Windows%2010.png" width="500">
</picture>\


### - Installation sur Linux

**1/ Ouvrir le terminal**\
**2/ Écrire la commande `$sudo apt-get install nmap -y` ; appuyer sur Entrée ; rentrer le mot de passe ; appuyer de nouveau sur Entrée**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Linux%201.png" width="500">
</picture>\
\
\
**3/ L'installation prend quelques secondes. A la réaparition de votre prompt, elle est terminée**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Linux%202.png" width="500">
</picture>\
\
\
**4/ Nmap est Installé. Vous pouvez vérifier la version en écrivant la commande `nmap -version`**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20Linux%203.png" width="500">
</picture>


### - Installation sur macOS

**1/ Télécharger Nmap sur le site officiel à l'adresse `https://nmap.org/download`**\
 \
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20macOS.png" width="500">
</picture>\
\
\
**2/ Suivre les étapes d'installation**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20macOS%201.png" width="300">
</picture>
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20macOS%202.png" width="300">
</picture>
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20macOS%203.png" width="300">
</picture>\
\
\
**3/ Nmap est installé**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Install%20macOS%204.png" width="500">
</picture>\



---

### :three:  Solutions aux problèmes connus et communs liés à l’installation et à la configuration

* Résoudre les problèmes de ping depuis un client Linux vers un serveur Windows Server
    - Situation initiale :
        - Deux machines fonctionnelles, un serveur Windows Server 2022 et un client Linux Ubuntu connectées sur un même réseau local
		- Les adresses IP fixes validées : `172.16.10.10` pour le Serveur et `172.16.10.20` pour le Client
  	- Le serveur Windows parvient à ping le client Ubuntu
  	- Le client Ubuntu ne parvient **_PAS_** à ping le serveur Windows
      
    - Résolution du problème  

**Situation de départ : le client Ubuntu ne parvient pas ping le serveur Windows**

![Image d'un terminal Ubuntu affichant un échec de ping](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%2010.png)
 
**1/ Ouvrir le menu Démarrer du Serveur Windows**\
**2/ Cliquer sur l'engrenage "Settings" ou "Paramètres"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%201.png" width="700">
</picture>\
\
\
**3/ Cliquer sur "Update & Security" ou "Mise à jour et sécurité"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%202.png" width="700">
</picture>\
\
\
**4/ Cliquer sur l'Onglet "Windows Security" ou "Sécurité Windows"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%203.png" width="700">
</picture>\
\
\
**5/ Cliquer sur "Firewall & network protection" ou "Pare-feu et protection réseau"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%204.png" width="700">
</picture>\
\
\
**6/ Cliquer sur "Advanced Settings" ou "Paramètres avancés"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%205.png" width="700">
</picture>\
\
\
**_(On peut remplacer les étapes 1 à 6 en tapant_ `firewall.cpl` _dans la barre de recherche afin d'arriver directement à l'étape 7)_**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%208.png" width="500">
</picture>
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%2011%20V2.png" width="500">  
</picture>\
\
\
**7/ Dans le volet de gauche, cliquer sur "Inbounds Rules" ou "Règles de trafic entrant"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%206.png" width="700">
</picture>\
\
\
**8/ Faites défiler la liste jusqu'à voir la ligne suivante : _File and Printer Sharing (Echo Request - ICMPv4-In)_**\
**9/ Faites un clic droit sur cette ligne et cliquez sur "Enable Rule" ou "Activer la règle"**\
\
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%207.png" width="700">
</picture>\
\
\
**10/ Si on lance maintenant une tentative de Ping depuis le Client Linux vers le Serveur Windows, la tentative est couronnée de succès.**
<picture>
  <img src="https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/capture/Ping%209.png" width="700">
</picture>



