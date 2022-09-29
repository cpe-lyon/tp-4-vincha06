Vincent CHAVES - 3ICS

# TP 4 - Gestion des paquets

## Exercice 1. Commandes de base

### 1. Commencez par mettre à jour votre système avec les commandes vues dans le cours.
- <code>sudo su</code>
- <code>apt update</code>
- <code>apt upgrade</code>

### 2. Créez un alias “maj” de la ou des commande(s) de la question précédente. Où faut-il enregistrer cet alias pour qu’il ne soit pas perdu au prochain redémarrage ?
- ![image](https://user-images.githubusercontent.com/113091304/192954647-5c836d28-3669-4129-a1e4-74c84d025012.png)
- Pour qu'il ne soit pas perdu il faut l'entrer dans le fichier .bashrc comme ceci :
- ![image](https://user-images.githubusercontent.com/113091304/192964554-4a709ea1-e084-44a5-956f-34d81e691136.png)
- Je vérifie si ça fonctionne :
- ![image](https://user-images.githubusercontent.com/113091304/192957228-f3b94889-bf8c-4207-b80e-2196a529e602.png)

### 3. Utilisez le fichier /var/log/dpkg.log pour obtenir les 5 derniers paquets installés sur votre machine.
- ![image](https://user-images.githubusercontent.com/113091304/192960259-f14c5930-1444-499c-a638-bb006d1604a7.png)

### 4. Listez les derniers paquets qui ont été installés explicitement avec la commande apt install
- ![image](https://user-images.githubusercontent.com/113091304/192960801-0874796e-2c7a-48e8-9938-a44d85a56cd6.png)

### 5. Utilisez les commandes dpkg et apt pour compter de deux manières différentes le nombre de total de paquets installés sur la machine (ne pas hésiter à consulter le manuel !). Comment explique-t-on la (petite) différence de comptage ? Pourquoi ne peut-on pas utiliser directement le fichier dpkg.log ?
- ![image](https://user-images.githubusercontent.com/113091304/192966279-902c5abc-6cfe-4053-864e-34cf57647aff.png)

### 6. Combien de paquets sont disponibles en téléchargement sur les dépôts Ubuntu ?

### 7. A quoi servent les paquets glances, tldr et hollywood ? Installez-les et testez-les.
### 8. Quels paquets proposent de jouer au sudoku ?

