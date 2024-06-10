# Projet : Utilisation de John the Ripper

## Introduction

Dans le cadre de notre formation TSSR à la Wild Code School, nous avons entrepris un projet visant à explorer et à démontrer l'utilisation de John the Ripper, l'un des outils de déchiffrement de mots de passe les plus célèbres et les plus efficaces. Ce projet se concentre sur la compréhension de ses fonctions, son installation et son utilisation pratique.

## Objectifs du Projet

1. **Comprendre les principes de base du hachage et du déchiffrement de mots de passe.**
2. **Installer John the Ripper sur différentes plateformes.**
3. **Explorer les caractéristiques et les capacités de John the Ripper.**
4. **Effectuer des attaques de mots de passe en utilisant John the Ripper.**
5. **Analyser et interpréter les résultats obtenus.**

## Présentation de John the Ripper

### Qu'est-ce que John the Ripper ?

John the Ripper est un outil open-source de déchiffrement de mots de passe, initialement développé pour Unix mais maintenant compatible avec plusieurs autres systèmes d'exploitation, dont Windows et macOS. Il est réputé pour sa rapidité et sa polyvalence, étant capable de déchiffrer une variété de types de hachage, tels que MD4, MD5, SHA1 et NTLM.

## Les membres du groupe 3
Vanessa : Product Owner semaine 1

Karim : Scrum Master semaine 1

Nabil : Product Owner semaine 2

Brice : Scrum Master semaine 2

## Les difficultés rencontrées, les solutions trouvées :
Pendant la phase de test, nous avons rencontré plusieurs difficultés :
1. Installation de John the Ripper : Nous avons eu du mal à installer John the Ripper sur Mac et sur Linux Ubuntu. Nous n'avons trouvé aucune solution viable pour ces systèmes, et avons donc opté pour Kali Linux, qui reste le système d'exploitation le plus adapté pour utiliser ce type de programme de pentesting.
2. Déchiffrement de mot de passe : Nous avons eu des difficultés à craquer le mot de passe d'un utilisateur. En effet, le type de hachage a changé ces dernières années. Par exemple, le hash yescript n'est pas pris en charge par John the Ripper (un test doit être effectué avec Hashcat).
   
## Les tests réalisés :
1. Installer John The Ripper sur plusieurs OS (Windows, Linux, Mac)
2. Décrypter un Hash en format md5 et sha1 sur un fichier .txt
3. Récuperer le mot de passe d'un utilisateur Linux/Windows et le décrypter 
