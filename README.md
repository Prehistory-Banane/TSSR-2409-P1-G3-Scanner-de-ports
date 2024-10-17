# TSSR-2409-P1-G3-Scanner-de-ports

# **README**

## **SOMMAIRE**

### 1. [Présentation du projet et des objectifs finaux](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/README.md#1-pr%C3%A9sentation-du-projet-et-des-objectifs-finaux-1)

### 2. [Introduction: mise en contexte](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/README.md#2--introduction-mise-en-contexte)
    
### 3. [Membres du groupe et rôle (s1 et s2)](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/README.md#3-membres-du-groupe-et-r%C3%B4le-s1-et-s2-1)
    
### 4. [Difficultés techniques rencontrés]()
    
### 5. [Solutions trouvées]
    
### 6. [Améliorations possibles: NSE](https://github.com/WildCodeSchool/TSSR-2409-P1-G3-Scanner-de-ports/blob/main/README.md#6-am%C3%A9liorations-possibles-nse-1)

---
### 1. Présentation du projet et des objectifs finaux

L'objectif de ce projet est de trouver les failles de sécurité d'un serveur en utilisant la métohde de scan de ports.  
Pour mener à bien ce projet, nous aurons recours au logiciel Nmap, qui va nous permettre de scanner les ports d'un serveur déterminé.  
Une fois ces failles repérées via le logiciel Nmap, il sera primordial de prendre les mesures nécessaires afin de les corriger, dans un soucis de sécurité.

---

### 2.  Introduction: mise en contexte

intro ici:

*
*
*
---

### 3. Membres du groupe et rôle (s1 et s2)  

Notre groupe est composé de 4 personnes : Elsa, Yohann, Lionel et Souhail.  
Voici les tâches et les rôles qui ont été affectés pour le premier et le deuxième sprint :  
> ### Premier sprint :
* **Yohann** : Occupant le rôle de *Scrum Master* sur le premier sprint, le rôle de Yohann a été d'organiser les réunions, de contribuer à la gestion du backlog product et de mener des rétrospectives.
Les tâches qui lui ont été affectées étaient les suivantes : faire des recherches sur Netcat et Nmap, comparer les deux logiciels afin de choisir lequel serait utilisé pour notre projet, installer Nmap et effectuer les premiers tests du logiciel.

* **Souhail** : Son rôle pour ce premier sprint a été *Product Owner*. Il était l'intermédiaire entre son équipe et le Product owner, il encourageait l'équipe et étant garant du bon déroulement de ce premier sprint.
Quant à ses tâches, il lui ont été confiés l'installation et le paramétrage du serveur (modification du nom, du groupe et de l'adresse Ip)

* **Elsa** : Les tâches d'Elsa pour ce premier sprint ont été l'installation d'un client ainsi que son paramétrage (création de la session utilisateur, paramétrage du mot de passe ainsi que de l'adresse Ip)

* **Lionel** : Lionel avait comme tâche de rédiger la documentation d'Nmap, d'installer le logiciel sur le client et de procéder à des tests.

> ### Deuxième sprint :
* **Lionel** : Sur ce deuxième sprint, Lionel a remplacé Souhail pour le rôle de *Product Owner*.  
Il lui a été attribuée comme tâche la finalisation de la rédaction du livrable "USER_GUIDE.md", ce qui permettra à n'importe quel utilisateur n'ayant jamais manipulé Nmap d'avoir une documentation complète sur son utilisation.  

* **Yohann** : La tâche affectée à Yohann était la rédaction du livrable "INSTALL.md", documentant les étapes à suivre pour l'installation du logiciel Nmap.  

* **Elsa et Souhail** : La rédaction du livrable "README.md" a été confiée à Elsa et Souhail pour ce deuxième sprint.


--- 

### 4. Difficultés techniques rencontrés

ici

* probleme de ping entre serveur et client : ! Yohann a déjà rédigé quelque chose; à voir
* ports fermés  
*
*

---

### 5. Solutions trouvées

ici

*
*
*
---

### 6. Améliorations possibles: NSE

Il est possible de rendre Nmap plus flexible et efficace en utilisant le moteur de script de Nmap (Nmap Scri^ting Engine - NSE). Effectivement NSE llie l'efficacité avec laquelle Nmap traite le réseau avec la souplesse d'un langage léger comme Lua, fournissant ainsi une infinité d'opportunités. Une documentation plus complète du NSE (y compris ses API) peut être obtenue sur https://nmap.org/nse. Le but du NSE est de fournir à Nmap une infrastructure flexible afin d'étendre ses capacités et ainsi offrir à ses utilisateurs une facon simple de créer leurs propres tests personnalisés.Le cadre d'usage du NSE englobe (mais encore une fois n'est pas limité à) :

- La détection de version évolué;
- La détection de Malware;
- La découverte du réseau et la collecte d'informations,...

Afin de refléter ces différents usages et pour simplifier le choix des scripts à employer, chaque script contient un champ qui l'associe a une ou plusieurs de ces catégories. Pour maintenir le lien entre scripts et catégories un fichier appelé script.db est installé avec les scripts distribués. Ainsi si par exemple vous voulez voir si une machine est infectée par un ver Nmap vous donne un script que vous pouvez facilement utiliser par la commande `nmap --script=malware ip-cible` afin d'analyser les résultats après coup.Les scripts de version sont systématiquement lancés de facon implicite lorsqu'un scan de scripts est invoqué. Le fichier script.db est lui même un script Lua et peut être mis à jour via l'option `--script-updatedb`.



