# **GUIDE D UTILISATION NMAP**

## **SOMMAIRE**

### 1. [Utilisation basique (Ubuntu)](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#1-utilisation-basique-ubuntu-1)

### 2. [Utilisation avancée](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#2--utilisation-avanc%C3%A9e-certaines-commandes-peuvent-n%C3%A9cessit%C3%A9-dutiliser-sudo)
    
### 3. [Exemple et interprétation du résultat](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#3--exemple-et-interpr%C3%A9tation-du-r%C3%A9sultat)

### 4.  [Scan personnalisé avec NSE](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/USER_GUIDE.md#4--scan-avanc%C3%A9-avec-nse)

---

### 1. Utilisation basique (Ubuntu)

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

### 2.  Utilisation avancée: certaines commandes peuvent nécessité d'utiliser `sudo`

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

### 3.  Exemple et interprétation du résultat

> ![capture cmd basique](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/8a152d6a65d29c57d7f1cd25c362bfda508c19d1/capture/Capture%20d'%C3%A9cran%202024-10-16%20123035.png)

- **Ligne 1** : Sur la ligne 1, nous voyons que l'utilisateur "wilder", depuis le client CLILIN01, lance une commande `nmap` vers un serveur ayant pour adresse IP `[172.16.10.10]`.
- **Ligne 2** : La ligne 2 indique le lancement du logiciel nmap, en précisant l'heure et la date.
- **Ligne 3** : Ici, il est annoncé que nous allons recevoir un rapport de scan des ports de l'adresse IP scannée.
- **Ligne 4** : Cette ligne fournit des informations concernant le délai de réponse du serveur (latence).
- **Ligne 5** : Cette ligne indique le nombre de ports fermés.
- **Lignes 6 à 10** : Ici, nous avons le détail des ports ouverts et des services associés à chacun d'eux.
- **Ligne 12** : Enfin, cette ligne nous informe que l'hôte a bien été scanné en 5,03 secondes.

---

### 4.  Scan avancé avec NSE 

Il est possible de rendre Nmap plus flexible et efficace en utilisant le moteur de script de Nmap (Nmap Scri^ting Engine - NSE). Effectivement NSE llie l'efficacité avec laquelle Nmap traite le réseau avec la souplesse d'un langage léger comme Lua, fournissant ainsi une infinité d'opportunités. Une documentation plus complète du NSE (y compris ses API) peut être obtenue sur https://nmap.org/nse. Le but du NSE est de fournir à Nmap une infrastructure flexible afin d'étendre ses capacités et ainsi offrir à ses utilisateurs une facon simple de créer leurs propres tests personnalisés.Le cadre d'usage du NSE englobe (mais encore une fois n'est pas limité à) :

* La détection de version évolué;
* La détection de Malware;
* La découverte du réseau et la collecte d'informations,...

Afin de refléter ces différents usages et pour simplifier le choix des scripts à employer, chaque script contient un champ qui l'associe a une ou plusieurs de ces catégories. Pour maintenir le lien entre scripts et catégories un fichier appelé script.db est installé avec les scripts distribués. Ainsi si par exemple vous voulez voir si une machine est infectée par un ver Nmap vous donne un script que vous pouvez facilement utiliser par la commande nmap --script=malware ip-cible afin d'analyser les résultats après coup.Les scripts de version sont systématiquement lancés de facon implicite lorsqu'un scan de scripts est invoqué. Le fichier script.db est lui même un script Lua et peut être mis à jour via l'option --script-updatedb.

- **Exemple de scan du port de serveur DHCP avec utilisation d'un NSE:**

> ![capture commande avec script](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/8e8bda68cd305d254ca48e75d36ac4dda22c7865/capture/scan%20avec%20script.png)
  
---


