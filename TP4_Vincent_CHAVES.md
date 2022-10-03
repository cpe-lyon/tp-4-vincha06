Vincent CHAVES - 3ICS

# TP 4 - Gestion des paquets

## Exercice 1. Commandes de base

### 1. Commencez par mettre à jour votre système avec les commandes vues dans le cours.
- <code>sudo su</code>
- <code>apt update</code>
- <code>apt upgrade</code>

### 2. Créez un alias “maj” de la ou des commande(s) de la question précédente. Où faut-il enregistrer cet alias pour qu’il ne soit pas perdu au prochain redémarrage ?
- ![image](https://user-images.githubusercontent.com/113091304/193025020-f5d8b6f3-aec3-4685-bb8e-f5ae13439daf.png)
- Pour qu'il ne soit pas perdu il faut l'entrer dans le fichier .bashrc comme ceci :
- ![image](https://user-images.githubusercontent.com/113091304/192964554-4a709ea1-e084-44a5-956f-34d81e691136.png)
- Je vérifie si ça fonctionne :
- ![image](https://user-images.githubusercontent.com/113091304/192957228-f3b94889-bf8c-4207-b80e-2196a529e602.png)
- Ça fonctionne bien

### 3. Utilisez le fichier /var/log/dpkg.log pour obtenir les 5 derniers paquets installés sur votre machine.
- ![image](https://user-images.githubusercontent.com/113091304/192960259-f14c5930-1444-499c-a638-bb006d1604a7.png)

### 4. Listez les derniers paquets qui ont été installés explicitement avec la commande apt install
- ![image](https://user-images.githubusercontent.com/113091304/192960801-0874796e-2c7a-48e8-9938-a44d85a56cd6.png)

### 5. Utilisez les commandes dpkg et apt pour compter de deux manières différentes le nombre de total de paquets installés sur la machine (ne pas hésiter à consulter le manuel !). Comment explique-t-on la (petite) différence de comptage ? Pourquoi ne peut-on pas utiliser directement le fichier dpkg.log ?
- ![image](https://user-images.githubusercontent.com/113091304/192966279-902c5abc-6cfe-4053-864e-34cf57647aff.png)
- 626 paquets et 619. Cette différence s'explique par le fait que la commande dpkg n'affiche pas les dépendances contrairement à la commande apt list.
- On ne peut pas directement utiliser le fichier dpkg car il ne liste pas uniquement les paquets installés.

### 6. Combien de paquets sont disponibles en téléchargement sur les dépôts Ubuntu ?
- ![image](https://user-images.githubusercontent.com/113091304/192971862-2c92ed70-437d-499f-bdbb-a35fcc514d65.png)
- 69053

### 7. A quoi servent les paquets glances, tldr et hollywood ? Installez-les et testez-les.
-  glances sert à afficher l'utilisation des ressources système :
- ![image](https://user-images.githubusercontent.com/113091304/192986761-2028f09d-7fbd-42f2-be1a-069794e10ced.png)
- "tldr" est un "manuel simplifié rédigé par la communauté" :
- ![image](https://user-images.githubusercontent.com/113091304/192985098-54ad3ecd-6b28-4c8c-9f25-4940e3226eda.png)
- "hollywood" ne sert à rien, ça reproduit un piratage selon les films hollywood.
- ![image](https://user-images.githubusercontent.com/113091304/193025119-c4de9af2-9f7e-41c0-92e6-478e7675f96a.png)

### 8. Quels paquets proposent de jouer au sudoku ?
- sudoku : <code>apt install sudoku</code>
- ![image](https://user-images.githubusercontent.com/113091304/192988491-f1ebcb3a-e169-4aa8-bc2a-9ccb8eca397e.png)

## Exercice 2

### A partir de quel paquet est installée la commande ls ?
- ls est installée dans le coeur du système (coreutils) et se retrouve aussi dans le paquet "klics-utils" :
- ![image](https://user-images.githubusercontent.com/113091304/192993078-e13a32b2-7532-45d8-860a-12c899fae20f.png)
### Comment obtenir cette information en une seule commande, pour n’importe quel programme ? 
- Comme vu à la question précédente, afin d'obtenir cette information en une seule commande, il faut taper : <code>dpkg -S ls | grep "/ls$"</code>
- ![image](https://user-images.githubusercontent.com/113091304/192993078-e13a32b2-7532-45d8-860a-12c899fae20f.png)

###  Utilisez la réponse à cette question pour écrire un script appelé origine-commande (sans l’extension .sh) prenant en argument le nom d’une commande, et indiquant quel paquet l’a installée.
- ![image](https://user-images.githubusercontent.com/113091304/193078585-deab378e-038a-4764-bd79-c3041a988e04.png)
- Je teste avec les commandes ls, nano et mkdir :
- ![image](https://user-images.githubusercontent.com/113091304/193023914-37ff50ce-6507-4d9d-a28a-90175f01a25f.png)
- ![image](https://user-images.githubusercontent.com/113091304/193024106-9d597f6f-e864-482c-89d9-5200677d4fe7.png)
- ![image](https://user-images.githubusercontent.com/113091304/193024150-3ad4d9a1-a118-459e-9a3f-7cd205e769f9.png)
- Le script fonctionne correctement.

## Exercice 3
### Ecrire une commande qui affiche “INSTALLÉ” ou “NON INSTALLÉ” selon le nom et le statut du package spécifié dans cette commande.
- <code>dpkg -l "nano" | grep "^i" && echo "INSTALLE" || echo "NON INSTALLE"</code>
- ![image](https://user-images.githubusercontent.com/113091304/193027137-485b05da-b28c-4807-bd92-ff67412dfbad.png)

## Exercice 4
### Lister les programmes livrés avec coreutils. En particulier, on remarque que l’un deux se nomme [. De quoi s’agit-il ?
- ![image](https://user-images.githubusercontent.com/113091304/193030047-4e8087e5-8e56-483d-9642-20b347c055f0.png)

## Exercice 5
### Installez les paquets emacs et lynx à l’aide de la version graphique d’aptitude (et prenez deux minutes pour vous renseigner et tester ces paquets).
- ![image](https://user-images.githubusercontent.com/113091304/193034660-73e75ca8-514d-497c-ae71-17e0ccac1449.png)
- <code>sudo su</code>
- <code>aptitude</code>
- lynx :
- ![image](https://user-images.githubusercontent.com/113091304/193044751-043170bb-3be0-4c22-b2a9-98a9b222a1c8.png)
- Emacs est un éditeur de texte et Lynx est un navigateur web rudimentaire (sans réelle interface graphique)

## Exercice 6
### 1. Installer la version Oracle de Java (avec l’ajout des PPA)
### sudo add-apt-repository ppa:linuxuprising/java
### sudo apt update
### sudo apt install oracle-java15-installer
- ![image](https://user-images.githubusercontent.com/113091304/193058246-1885c19e-2598-443a-ac45-376c56bb2ff5.png)
- ![image](https://user-images.githubusercontent.com/113091304/193058646-62c859a7-64f8-4530-ae4e-ee5c350c156f.png)
- ![image](https://user-images.githubusercontent.com/113091304/193058931-4cefdbd2-d66f-4363-9ec2-75a2177f0442.png)
### 2. Vérifiez qu’un nouveau fichier a été créé dans /etc/apt/sources.list.d. Que contient-il ?
- ![image](https://user-images.githubusercontent.com/113091304/193074659-d0487321-3138-4c8a-b182-76bde9a743ef.png)
- Il contient ça :
- ![image](https://user-images.githubusercontent.com/113091304/193075134-202989d6-51c6-4879-b90d-56a8f58d6085.png)


## Exercice 7
### 1. Commencez par cloner le dépôt git suivant :
### git clone https://gitlab.com/jallbrit/cbonsai
### Ceci permet de récupérer en local le code source du logiciel cbonsai.!
- ![image](https://user-images.githubusercontent.com/113091304/193079845-f0b3298b-7f07-4d9c-b00c-9988ae37136b.png)

### 2. Rendez vous dans le dossier cbonsai. Un fichier README.md) est livré avec les sources, et vous explique comment compiler le programme (vous pouvez installer un lecteur de Markdown pour Bash, comme mdless pour vous faciliter la lecture de ce type de fichiers). Un fichier Makefile est également présent. Un Makefile est un fichier utilisé par l’outil make, et contient toutes les directives de compilation d’un logiciel. Un Makefile définit un certain nombre de règles permettant de construire des cibles. Les cibles les plus communes étant install (pour la compilation et l’installation du logiciel) et clean (pour sa suppression). En suivant les consignes du fichier README.md, et en installant les éventuels paquets manquants, compilez ce programme et installez le en local.
- ![image](https://user-images.githubusercontent.com/113091304/193080077-4f99bf04-491b-4f9b-b0f7-ed3ee48dc69e.png)
- On peut désormais lancer cbonsai avec :
- ![image](https://user-images.githubusercontent.com/113091304/193081050-150e008c-ca85-48bc-8410-8ee3102ef90e.png)
- ![image](https://user-images.githubusercontent.com/113091304/193081313-5e3a30d0-bea0-435e-8a58-8e81e0fad940.png)

### 3. Malheureusement, cette installation “à la main” fait qu’on ne dispose pas des bénéfices de la gestion de paquets apportés par dpkg ou apt. Heureusement, il est possible de transformer un logiciel installé “à la main” en un paquet, et de le gérer ensuite avec apt ; c’est ce que permet par exemple l’outil checkinstall.
- J'utilise donc la commande checkinstall :
- ![image](https://user-images.githubusercontent.com/113091304/193082057-515b8e63-fd7e-4bd8-b072-a9ecb706c4c8.png)
- Cbonsai est désormais un paquet :
- ![image](https://user-images.githubusercontent.com/113091304/193082456-ee5168b3-c000-4f1b-ba45-0bb1fef3852a.png)

### 4. Recommencez la compilation à l’aide de checkinstall
### sudo checkinstall
- Voir question précédente
### Un paquet a été créé (fichier xxx.deb), et le logiciel est à présent installé (tapez cbonsai depuis n’importe quel dossier pour vous en assurer) ; on peut vérifier par exemple avec aptitude qu’il provient bien du paquet qu’on a créé avec checkinstall. Vous pouvez à présent profiter d’un instant de zenitude avant de passer au dernier exercice.
- Vérification de la présence du fichier .deb :
- ![image](https://user-images.githubusercontent.com/113091304/193083290-e6148131-38ba-44ec-abe6-1c04f5cf59a7.png)
- cbonsai s'éxecute bien depuis n'importe quel dossier
- Avec aptitude je peux voir que cbonsai a bien été "installé localement" et avec checkinstall :
- ![image](https://user-images.githubusercontent.com/113091304/193085543-50207bb6-e437-4e94-b21a-3f00396cb580.png)

## Exercice 8
### Dans cet exercice, vous allez créer vos propres paquets et dépôts, ce qui vous permettra de gérer les programmes que vous écrivez comme s’ils provenaient de dépôts officiels.
### 1. Dans le dossier scripts créé lors du TP 2, créez un sous-dossier origine-commande où vous créerez un sous-dossier DEBIAN, ainsi que l’arborescence usr/local/bin où vous placerez le script écrit à l’exercice 2
- ![image](https://user-images.githubusercontent.com/113091304/193523595-f82108f4-4c16-4ee9-b91a-514c398b7ccc.png)
- ![image](https://user-images.githubusercontent.com/113091304/193523998-2f0bcfa4-eff4-45c0-a8ea-35b7f241d8fa.png)

### 2. Dans le dossier DEBIAN, créez un fichier control avec les champs suivants :
- ![image](https://user-images.githubusercontent.com/113091304/193530355-64603c47-a63e-4b0e-9ccc-07b47792dd55.png)
- ![image](https://user-images.githubusercontent.com/113091304/193531282-6b371990-f2ed-42b2-b23a-3ccc6fc7080b.png)

### 3. Revenez dans le dossier parent de origine-commande (normalement, c’est votre $HOME) et tapez la commande suivante pour construire le paquet :
### dpkg-deb --build origine-commande
### Félicitations ! Vous avez créé votre propre paquet !
- ![image](https://user-images.githubusercontent.com/113091304/193534326-5523338e-76c1-41a9-a4b1-0f97e63504e4.png)



















