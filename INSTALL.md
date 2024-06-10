# Installation John The Ripper sur Ubuntu Linux

## Mettre à jour votre OS
Commande : Sudo apt update && upgrade

Sudo (superuser do) : permet d’exécuter une commande avec les privilèges administratifs
comme l’administration du système, l’installation ou la mise à jours de logiciel.

Apt (advanced package tool) : est utilisé pour effectuer des opérations telles que l’installation, la mise à jour, la suppression et la gestion des paquets logiciels.

&& : est un opérateur qui est utilisé pour exécuter plusieurs commandes en séquence, l'une après l'autre, et seulement si la commande précédente réussit.

Sudo apt update : Met à jour la liste des paquets disponibles à partir des dépôts configurés sur le système. Cela ne met pas à jour les paquets eux-mêmes, mais synchronise l'index local des paquets avec les sources en ligne.

Sudo apt upgrade : Met à jour tous les paquets installés sur le système vers les versions les plus récentes disponibles. Après avoir mis à jour la liste des paquets avec apt update, cette commande effectue la mise à jour proprement dite.

## Installer John the ripper
1. méthode : taper la commande : sudo apt Install john
   
Install : sous commande d’apt qui indique que vous installez un nouveau paquet de logiciel sur
votre système

John : C'est le nom du paquet logiciel que vous souhaitez installer. Dans ce cas, "john" fait
référence à "John the Ripper ».



2. méthode : taper la commande : sudo snap install john-the-ripper
   
Sudo (superuser do) : permet d’exécuter une commande avec les privilèges administratifs
comme l’administration du système, l’installation ou la mise à jours de logiciel.

Snap : est un système de gestion de paquets et de distribution de logiciels pour les distributions Linux. Il permet d'installer et de gérer des applications en utilisant des "snaps", qui sont des paquets logiciels autonomes contenant toutes les dépendances nécessaires.

Install : sous commande d’apt qui indique que vous installez un nouveau paquet de logiciel sur votre système.

john-the-ripper : est le nom du snap que vous souhaitez installer. Dans ce cas, "john-the-ripper" fait référence au snap contenant le logiciel "John the Ripper".

## Vérifez que John the ripper et correctement installé
Commande : john

En tapant John vous pourrez bien vérifier que la dernière version de John the Ripper est installée sur votre système.

***Attention, bien que John the Ripper soit correctement installé sur Ubuntu Linux, il s'est avéré pendant notre phase de test qu'il ne fonctionnait pas correctement***


# Installation John The Ripper sur Kali Linux

L'installation de John the Ripper sur Kali Linux est assez simple puisque celui-ci est installé par défaut. Il vous faudra tout de même effectuer les mises à jours du sytème.

Commande : sudo apt update && apt upgrade

Sudo (superuser do) : permet d’exécuter une commande avec les privilèges administratifs
comme l’administration du système, l’installation ou la mise à jours de logiciel.

Apt (advanced package tool) : est utilisé pour effectuer des opérations telles que l’installation, la
mise à jour, la suppression et la gestion des paquets logiciels.

&& : est un opérateur qui est utilisé pour exécuter plusieurs commandes en séquence, l'une après l'autre, et seulement si la commande précédente réussit.

Sudo apt update : Met à jour la liste des paquets disponibles à partir des dépôts configurés sur
le système. Cela ne met pas à jour les paquets eux-mêmes, mais synchronise l'index local des
paquets avec les sources en ligne.

Sudo apt upgrade : Met à jour tous les paquets installés sur le système vers les versions les plus
récentes disponibles. Après avoir mis à jour la liste des paquets avec apt update, cette
commande effectue la mise à jour proprement dite.

## Vérifez que John the ripper et correctement installé
Commande : john

En tapant John vous pourrez bien vérifier que la dernière version de John the Ripper est installée sur votre système.


# Installation John The Ripper sur Windows 10/11

## Télécharger la dernière version de John The Ripper

Aller sur le site https://www.openwall.com/john/ Puis télécharger le fichier Zip en fonction des bits de votre système 32 ou 64 bits. Vous pouvez connaitre cette valeur en allant dans “Informations système“ depuis le menu “Démarrer“.

<img width="854" alt="Capture d’écran 2024-06-06 à 16 03 41" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/1cbe7ab4-dbec-466c-b0a7-66edcf12346d">

## Installation 

1. Allez dans le dossier Téléchargements, puis double-cliquez sur le fichier Zip John-1.9.0-jumbo-win64, vous voilà sur le fichier principal

<img width="830" alt="Capture d’écran 2024-06-06 à 16 05 12" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/fcb3aa75-a8e5-4ff1-a252-30f0d20815f0">
 
2.  Prenez ce fichier, coupez et collez sur le disque (C:) puis renommez le dossier JohnTheRipper

<img width="844" alt="Capture d’écran 2024-06-06 à 16 06 41" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/d2d0fc55-a7ee-4987-81cd-ed0a8977cd75">

3. Double cliquez sur le fichier JohnTheRipper, puis cliquez sur le dossier d’exécution nommé “run“. Une fois les étapes faites taper Cmd dans la barre de chemin, puis “Entrée“.
   
<img width="849" alt="Capture d’écran 2024-06-06 à 16 12 04" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/d4b64bf8-e26b-4851-8258-f92ed6df5449">

5.  Le terminal windows s’ouvrira, puis taper “dir“ pour répertorier tous les fichiers et dossiers.

6. Pour bien vérifier que John The Ripper fonctionne correctement tapé “John“. John The Ripper est installé avec succès.

<img width="830" alt="Capture d’écran 2024-06-06 à 16 12 35" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/b94713b9-e7e7-4b02-afd6-dec6c79d51b2">


# Installation John The Ripper sur Mac Os

## Installation Homebrew

Homebrew est un outil puissant et pratique pour gérer les logiciels sur macOS, rendant le processus d'installation et de mise à jour des logiciels beaucoup plus simple et plus efficace. Ouvrir un terminal et tapez la commande suivante.

Commande : /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

/bin/bash -c : permet de lancer un nouveau processus dans le shell bash

$(curl -fsSL : permet d’utiliser « curl » pour télécharger un fichier, et les options « -fssl » qui permettent de suivre les redirections, utiliser le mode silencieux, et afficher les barres de progression.

https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh) : l’adresse du fichier à télécharger (John the ripper).

## Installation John the ripper

Sur ce même terminal tapez la commande suivante pour installer John the ripper.

Commande : brew install john

brew : la commande qui permet d’interagir avec homebrew

install: la sous commande de brew pour installer le package

john : C'est le nom du paquet logiciel que vous souhaitez installer. Dans ce cas, "john" fait référence à "John the Ripper ».

## Vérifez que John the ripper et correctement installé
Commande : john

En tapant John vous pourrez bien vérifier que la dernière version de John the Ripper est installée sur votre système.


