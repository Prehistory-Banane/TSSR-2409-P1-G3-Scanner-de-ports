# **DOC. TECHNIQUE**

## **SOMMAIRE**

### 1. [Prérequis techniques](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/edit/main/INSTALL.md#1-pr%C3%A9requis-techniques-1)

### 2. [Étapes d'installation et de conf. : instruction étape par étape](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/edit/main/INSTALL.md#2--%C3%A9tapes-dinstallation-et-de-conf--instruction-%C3%A9tape-par-%C3%A9tape)
    
### 3. [FAQ : solutions aux problèmes connus et communs liés à l’installation et à la configuration](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/edit/main/INSTALL.md#3--faq--solutions-aux-probl%C3%A8mes-connus-et-communs-li%C3%A9s-%C3%A0-linstallation-et-%C3%A0-la-configuration) 
    
---

### 1. Prérequis techniques

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
        - Client léger : Machine qui dépend fortement d'un serveur pour ses opérations (exemple : client RDP ou VDI).
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

### 2.  Étapes d'installation et de conf. : instruction étape par étape

intro ici:

*
*
*

---

### 3.  FAQ : solutions aux problèmes connus et communs liés à l’installation et à la configuration

* Résoudre les problèmes de ping depuis un client Linux vers un serveur Windows Server
    - Situation initiale :
        - Deux machines fonctionnelles, un serveur et un client
	    - Nmap installé sur le client
	    - Les adresses IP fixes validées
      
    - Résolution du problème

|    Méthode   |     Astuce       |  
| :------------ |:-------------:|    
| 1/ Ouvrir le menu Démarrer du Serveru Windows     |     On peut remplacer   |    
| 2/ Cliquer sur l'engrenage "Settings" ou "Paramètres"     |     les étapes 1 à 6    |    
| 3/ Cliquer sur "Update & Security" ou "Mise à jour et sécurité" |    en tapant :  `firewall.cpl`    |    
| 4/ Cliquer sur l'Onglet "Windows Security"	ou "Sécurité Windows" |     puis en appuyant sur Entrée   |    
| 5/ Cliquer sur "Firewall & network protection" ou "Pare-feu et protection réseau" |    dans la   |    
| 6/ Cliquer sur "Advanced Settings" ou Paramètres avancés |   Recherche Windows    |    
| 7/ Dans le volet de gauche, cliquer sur "Inbounds Rules" ou "Règles de trafic entrant" |        |
| 8/ Faites défiler la liste jusqu'à voir la ligne suivante : |       |
| 9/ *File and Printer Sharing (Echo Request - ICMPv4-In)* |       |
| 10/ Faites un clic droit sur cette ligne et cliquez sur "Enable Rule" ou "Activer la règle" |       |

.  
    - Si on lance maintenant une tentative de Ping depuis le Client Linux vers le Serveur Windows, la tentative est couronné de succès.


*
*

