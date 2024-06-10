# JOHN THE RIPPER

John the Ripper est l'un des outils de déchiffrement de mots de passe les plus célèbres, les plus appréciés et les plus polyvalents. Il allie une grande rapidité de déchiffrement à une compatibilité étendue avec une variété impressionnante de types de hachage.

Initialement, il a été conçu que pour le système d’exploitation Unix, mais il peut maintenant être utilisé sur plusieurs autres plates-formes, telles que Windows, Mac, etc. Il a été publié pour la première fois en 1996 par OpenWall. Sa dernière version est la 1.9.0 qui a été publiée en 2019.

## Qu’est ce que le Hachage (Hash) ?

Un hachage permet de transformer des données de longueur variable en une représentation de longueur fixe. Cela masque la valeur originale des données en les passant à travers un algorithme de hachage. Parmi les algorithmes de hachage populaires, on trouve MD4, MD5, SHA1 et NTLM.

Illustrons ce concept avec un exemple :

Si nous prenons "adil", une chaîne de 4 caractères - et que nous l'exécutons à travers un algorithme de hachage MD5, nous nous retrouverons avec une sortie de :
`5c3bea5d394835b2af9d2cfd632147f8` un hachage MD5 standard de 32 caractères.

De même, si nous prenons "professeuradil", une chaîne de 14 caractères - et que nous l'exécutons à travers le même algorithme de hachage MD5, nous nous retrouvons avec une sortie de :
`063ad290fafcaac17643cbf488b896a5` un autre hachage MD5 standard de 32 caractères.

## Qu'est-ce qui garantit la sécurité des hashs ?

Les hashs sont sécurisés grâce à plusieurs caractéristiques clés : ils sont résistants aux collisions, ce qui rend presque impossible de trouver deux ensembles de données différents produisant le même hash. Ils offrent une résistance à la préimage, empêchant de retrouver les données d'origine à partir du hash, et ils présentent un effet avalanche, où un petit changement dans les données d'entrée entraîne un changement significatif et imprévisible dans le hash. Ces propriétés assurent la sécurité et la fiabilité des hashs pour des applications comme la protection des mots de passe, l'intégrité des fichiers et les signatures numériques.

## La mission de John …

Même si un algorithme de hachage n'est pas réversible, il est toujours possible de casser des hashs. Par exemple, si vous avez la version hachée d'un mot de passe et que vous connaissez l'algorithme utilisé, vous pouvez créer un dictionnaire en hachant un grand nombre de mots. Ensuite, en comparant ces hashs avec celui que vous essayez de casser, vous pouvez trouver une correspondance. Si une correspondance est trouvée, vous connaissez le mot de passe original. Ce processus est appelé une attaque de dictionnaire. John the ripper (l’éventreur en français), souvent abrégé en John, est un outil permettant de mener des attaques de force brute rapides sur divers types de hashs.

**Le bon tuyau** : certains sites comme [hashes.com](https://hashes.com/en/decrypt/hash) vous permettent de déchiffrer certains hashs.

# PREMIERE MISE EN SITUATION DE JOHN THE RIPPER 

## Contexte pour un OS Kali Linux: 

L’objectif est de décrypter le Hash suivant : 1A732667F3917C0F4AA98BB13011B9090C6F8065

1. Copier le hash 1A732667F3917C0F4AA98BB13011B9090C6F8065 dans un fichier .txt

Commande à taper :
- touch hash.txt
- nano hash.txt et coller le hash 1A732667F3917C0F4AA98BB13011B9090C6F8065, puis enregistrer avec la commande control^ + x 

Vérifiez que le hash ait correctement été collé dans le fichier .txt avec la commande cat hash.txt

2.  Naviguer vers le répertoire contenant le fichier de hachage cd /chemin/vers/le/dossier

Puis lancer la commande suivante : john hash.txt 

<img width="593" alt="Capture d’écran 2024-06-06 à 17 49 29" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/0e1fedfd-bd4c-4cf5-8725-5dc12a540935">

Observation : Le message de John the ripper nous indique que le type de hachage détecté est “Raw-SHA1“, mais il reconnait également d’autres types possibles comme “Raw-SHA1-AxCrypt“, “Raw-SHA1-Linkedin“ et “ripemd-160“. Il suggère d’utiliser les options “—format=Raw-SHA1-AxCryp“, “—format=Raw-SHA1-Linkedin“ et “—format=ripemd-160“pour forcer le chargement des hachages sous ces formats spécifiques. 

3. Suite au message de John the ripper, nous allons taper la commande suivante pour lui préciser le type du hash qu'on lui demande de décrypter.

Commande : john --format=Raw-SHA1-Axcrypt hash.txt

Le processsus de décryptage jusquà trouver le mot hashé , dans notre exemple le mot Kangeroo 

<img width="595" alt="Capture d’écran 2024-06-06 à 17 52 07" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/276031cf-54e9-46a2-85fd-714b70fe0a12">

4. nous utiliserons la commande John —show hash.txt pour afficher le résultat, dans notre exemple le mot Kangeroo. 

***NOTE***

Il est difficile de donner une estimation précise sans connaître les détails exacts de votre configuration et de vos paramètres d'attaque. Cependant, voici quelques points de référence basés sur des scénarios typiques : 

- Avec un CPU puissant et OpenMP : Un processeur moderne avec plusieurs cœurs (8-16 cœurs) peut tester des centaines de milliers de combinaisons par seconde pour des hachages SHA-512.

- Avec un GPU (processeur graphique) puissant : Les GPU modernes (comme les NVIDIA RTX 3080 ou 3090) peuvent atteindre des millions de hachages par seconde.

- Délai pour des mots de passe simples vs. complexes : Mots de passe simples (par exemple, des mots de passe courants ou des variations simples) peuvent être craqués en quelques secondes à quelques minutes avec un bon dictionnaire. Mots de passe complexes (aléatoires, longs, avec des caractères spéciaux) peuvent prendre des jours, des semaines, voire des mois, en fonction de la longueur et de la complexité.

En résumé le délai de décryptage peut varier de quelques secondes à des centaines d'années en fonction de la complexité du mot de passe.

# DEUXIEME MISE EN SITUATION DE JOHN THE RIPPER 

## Contexte pour un OS Kali Linux:

Dans cet exercice pratique, nous allons tenter de retrouver le mot de passe oublié d'un utilisateur en utilisant l'outil John the Ripper. Cet outil est particulièrement efficace pour les tests de sécurité, car il permet de détecter les vulnérabilités liées aux mots de passe faibles ou mal protégés. Nous allons passer par les différentes étapes de ce processus, depuis l'obtention du fichier contenant les mots de passe hachés jusqu'à la configuration et l'exécution de John the Ripper pour déchiffrer le mot de passe. Ce type d'exercice est crucial pour comprendre l'importance de choisir des mots de passe robustes et pour apprendre les techniques utilisées par les administrateurs systèmes et les experts en sécurité pour sécuriser les comptes utilisateurs.

1. Préparation de l'environnement :
- Installer Kali Linux, John the ripper est installé par défaut, néanmoins pensez à effectuer les mises à jour de votre OS (voir fichier INSTALL.md)
- Assurez-vous d'avoir les permissions nécessaires pour exécuter John the Ripper et accéder aux fichiers de mots de passe.

2. Obtention du fichier contenant les mots de passe hachés :
Localisez le fichier de mots de passe hachés. Sur un système Unix/Linux, il s'agit souvent du fichier /etc/shadow.

Commande à taper :
- cd ../.. (vous permez de remonter deux niveaux dans l'arborescence des répertoires par rapport à votre position actuelle.)
- cd etc
- sudo cat shadow

Une fois le fichier 'shadow' affiché, seules les deux dernières lignes nous intéressent

![Capture d’écran 2024-05-31 à 10 25 37](https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/37205721-ae4f-4aa2-ae90-844fa7a5bd58)

Nous constatons que nous avons deux utilisateurs, Nabil et Pierre. Dans notre exercice nous souhaitons récupérer le mot de passe de Pierre. 

Le $ indique le type de HASH :

$1$ = MD5 hashing algorithm.
$2$ =Blowfish Algorithm.
$2a$=eksblowfish Algorithm
$5$ =SHA-256 Algorithm
$6$ =SHA-512 Algorithm
$y$ indique qu'il s'agit de yescrypt, un schéma de hachage récent utilisé par défaut dans Debian 11, Fedora 35+, et Kali Linux 2021.1+.

## Problématique : 

le mot de passe de Pierre commence par $y$ ce qui veux dire qu’il s’agit d’un schéma de hachage yescrypt qui n’est pas pris en charge par John the ripper. 

## Solution :

Nous allons essayé de modifier le fichier /etc/pam.d/common-password pour que celui-ci hache le mot de passe en format $6$ (SHA-512). Le fichier common-password est une composante importante du système PAM (Pluggable Authentication Modules) sur les systèmes Unix/Linux. Il est utilisé pour configurer les règles de gestion des mots de passe, telles que les politiques de complexité, les contrôles de qualité et les exigences de changement de mot de passe.

Commande à taper depuis un terminal : 

- cd ../..
- cd etc/pam.d
- file common-password (l’objectif et de connaitre la nature du fichier pour le modifier il s'agit d'un fichier ASCII text).

Pour le modifier nous allons utiliser la commande "nano"

<img width="560" alt="Capture d’écran 2024-06-04 à 21 58 50" src="https://github.com/Salemnabil44/Projet1-Johntheripper/assets/161028838/f0653ad6-cbaa-431c-b255-e671847568a7">

Cherchez une ligne : password       [success=1 default=ignore]      pam_unix.so obscure yescrypt

Et changez là en : 

password        [success=1 default=ignore]      pam_unix.so obscure sha512

## Malheureusement, malgré la modification du fichier common-password, nous n'avons pas réussi à changer le format de hachage. La mise en situation ne pourra donc pas être menée à son terme.

## Contexte pour un os Windows Server:

# Récupérer Hash mot de passe administrateur dans windows server 2022


Etant bloqué sur le décryptage de hachage de type yescrypt, nous avons décidé de contourner le problème par l'intermédiaire de l'application Mimikatz. Cet outil permet de récupérer le mots de passe en SHA1 ce qui enlève le problème du hachage de type yescrypt que nous pensions indéchiffrable par l'intermédiaire de John The Ripper.


Mimikatz est une alternative puissante pour extraire les hachages de mots de passe. Voici comment l'utiliser sur Windows Server 2022 :



1. **Télécharger Mimikatz :**
   -  Aller sur le dépôt GitHub officiel de Mimikatz : [Mimikatz GitHub](https://github.com/gentilkiwi/mimikatz).


![Lien recup mimikatz](https://github.com/bbrice28/wild-project/assets/169658100/0b5bc7da-51ff-41a7-8cac-a0f5f5a0de7c)







Si on ouvre le fichier Readme de Mimikatz, on constate qu’il est très bien expliqué, comme on peut le constater, il montre les commandes principales à taper ainsi que le résultat, voici une copie d’écran :


![exemple du readme pour mimikatz](https://github.com/bbrice28/wild-project/assets/169658100/3c659b68-4719-4d2d-9f74-bd7675734eb1)











- <a name="_hlk168611094"></a>**Préparer Mimikatz :**
- Décompresser le fichier téléchargé dans un répertoire accessible, par exemple C:\tools\mimikatz
- **Exécuter Mimikatz avec des privilèges administratifs** 
- <a name="_hlk168613955"></a> Ouvrir l'invite de commande en tant qu'administrateur

 

![command prompt administrator](https://github.com/bbrice28/wild-project/assets/169658100/a15c3130-c5e4-4638-8495-62cddf78ed45)






- Se rendre dans le répertoire de Mimikatz

 
![repertoire mimikat commandes](https://github.com/bbrice28/wild-project/assets/169658100/e9d0b0c2-9324-4ae7-b29d-3f620f519f99)






- Exécuter Mimikatz
![lancement mimicatz](https://github.com/bbrice28/wild-project/assets/169658100/a175b0ce-ee9a-48ca-9a7d-d6eeea11bd41)

 


- Voici le terminal Mimikatz une fois lancé
  
 
![mimicatz1](https://github.com/bbrice28/wild-project/assets/169658100/074ab802-95db-408d-b2de-3264ef3af3bc)





- Taper la première commande
  
 ![premiere commande](https://github.com/bbrice28/wild-project/assets/169658100/37ed1fdc-a76f-4894-8542-1ff78afbe50e)






La commande ` privilege::debug ` dans Mimikatz sert à activer le privilège « SeDebugPrivilege » pour le processus en cours. Ce privilège est nécessaire pour permettre à Mimikatz d'accéder à certaines fonctions critiques du système, notamment pour lire les informations de sécurité et les données sensibles stockées en mémoire.

**Pourquoi activer SeDebugPrivilege ?**

- **Accès aux informations sensibles** : Permet à Mimikatz de lire les informations d'authentification stockées en mémoire par des processus comme lsass.exe (Local Security Authority Subsystem Service). Ces informations peuvent inclure des hachages de mots de passe, des tickets Kerberos, des mots de passe en clair, etc.
- **Interaction avec d'autres processus** : Permet d'accéder et de manipuler des processus qui, autrement, seraient protégés ou limités en termes de permissions d'accès.




- Taper la deuxième et dernière commande


![command sekurlsa](https://github.com/bbrice28/wild-project/assets/169658100/8981ba5d-3215-4168-9772-fbb1726fa681)




La commande sekurlsa dans Mimikatz est une commande qui permet d'accéder aux informations relatives aux processus d'authentification en mémoire sur un système Windows. Elle est principalement utilisée pour extraire les informations de connexion, telles que les hachages de mots de passe, les tickets Kerberos, et d'autres données sensibles stockées par le système pour gérer les authentifications.

**Détails sur sekurlsa**

- **Objectif** : La commande sekurlsa est utilisée pour interagir avec le sous-système de sécurité Local Security Authority (LSA) de Windows, qui gère l'authentification et la sécurité des comptes utilisateur locaux et des ressources du système.
- **Fonctionnalités** : Elle offre plusieurs sous-commandes qui permettent d'accéder à différentes parties de la mémoire où sont stockées les informations d'authentification, telles que les hachages de mots de passe et les tickets Kerberos.

**Principales sous-commandes de sekurlsa**

- **` sekurlsa::logonpasswords `** :

Cette sous-commande extrait les informations de connexion stockées en mémoire, y compris les hachages de mots de passe et, dans certains cas, les mots de passe en clair des comptes utilisateur.

- **` sekurlsa::tickets `** :

Elle permet d'afficher les tickets Kerberos (TGT et TGS) actuellement disponibles sur le système. Ces tickets peuvent être utilisés pour accéder à des ressources réseau.


- **` sekurlsa::pth `** :

Utilisé pour l'authentification Pass-the-Hash, cette sous-commande permet de créer un jeton d'accès en utilisant un hachage de mot de passe plutôt que le mot de passe en clair.

- **` sekurlsa::ekeys `** :

Affiche les clés d'exportation de session (session keys) qui peuvent être utilisées pour déchiffrer les communications chiffrées entre les clients et les serveurs.

**Resultat de la dernière commande ` sekurlsa::logonpasswords `**

 
![resultat commande principale sekurla](https://github.com/bbrice28/wild-project/assets/169658100/1ce84d28-ddde-4abb-ae8f-3f12f2e6f17b)






**Explications données intéressantes dont Hash du mot de passe admin:**

- **NTLM** : 8846f7eaee8fb117ad06bdd830b7586c

C'est le hachage NTLM du mot de passe de l'utilisateur Administrator.

- **SHA1** : 1e9b6ec29919db9e0d824e4740d84b14a6299e6d

C'est le hachage SHA1 du mot de passe de l'utilisateur Administrator.

- **DAPI (dpapi)** :

Les informations sous dpapi montrent que des données protégées par la Data Protection API peuvent être présentes.

**Conclusion** : il ne reste plus qu’à se connecter en SSH à windows server 2022 pour transférer ce mot de passe de type SHA1 et le déchiffrer




