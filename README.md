# SAE 3.02 - Solution de consultation centralisée de journaux système

Ce dépôt contient le rendu final de mon projet de SAE 3.02 (BUT Réseaux & Télécoms).
Il s'agit d'une application Web développée en Python (Flask) permettant de surveiller les logs système (/var/log/syslog) de plusieurs serveurs distants via une interface unique.

## Contenu du dépôt

* **SAE302_BenOmrane.tar.gz** : L'archive complète du code source, prête à être déployée.
* **Documentation SAE 3.02.pdf** : Le rapport technique expliquant les choix d'architecture (SSH, droits bit-à-bit, etc.).
* **Manuel d'Installation.pdf** : Le guide utilisateur pour installer et utiliser l'application.

## Fonctionnalités principales

L'application répond au cahier des charges avec les fonctionnalités suivantes :
* **Authentification sécurisée** : Les mots de passe sont hachés en SHA-256 (via hashlib).
* **Gestion centralisée** : Ajout et suppression de serveurs à surveiller via leur adresse IP.
* **Lecture optimisée** : Récupération des 100 dernières lignes de logs via la commande 'tail' sur SSH (librairie Paramiko), pour éviter de surcharger le réseau.
* **Gestion des privilèges** : Système de droits géré bit-à-bit (Utilisateur, Gestionnaire, Administrateur).

## Stack Technique

* Langage : Python 3
* Framework Web : Flask
* Base de données : MariaDB
* Protocole distant : SSH (Paramiko)
* Frontend : HTML / CSS

## Instructions d'installation

Pour tester le projet, il faut récupérer l'archive présente dans ce dépôt.

1. Télécharger et extraire l'archive :
   tar -xzvf SAE302_BenOmrane.tar.gz

2. Se rendre dans le dossier extrait :
   cd Rendu_SAE302

3. Lancer le script d'installation automatique (nécessite les droits sudo) :
   chmod +x install.sh
   ./install.sh

4. Activer l'environnement virtuel et lancer l'application :
   source venv/bin/activate
   python3 app.py

L'application sera accessible sur http://localhost:5000.

## Auteur
Yacine Ben Omrane
