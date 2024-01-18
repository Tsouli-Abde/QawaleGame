
# ReadMe - Jeu Qawale

Ce dossier contient l'application "Jeu Qawale", développée par Yacin Djaoui, Tsouli Abderahmane, Lilia Chebili, Sonia Reghis, étudiants en 3ème année de licence DANT à Sorbonne Université.

 L'application est réalisée à 100% en Java, utilisant le modèle de conception MVC avec JavaFX pour les vues et les interfaces 3D, et une architecture réseau client/server pour connecter les joueurs du monde.



## Auteurs

- [@Djaoui-Yacine](https://www.github.com/azy-hub)
- [@Reghis-Sonia](https://github.com/Soniareghis)
- [@Chebili-Lilia](https://github.com/LiliaChebili)
- [@Tsouli-Abderrahmane](https://www.github.com/Tsouli-Abde)









## Règles du jeu

[Documentation](https://cdn.1j1ju.com/medias/0b/42/6b-qawale-regle.pdf)


## Installation de JavaFX


JavaFX n’est pas fourni avec les JDK récents (11 et supérieur).


L’implantation de JavaFX que nous utiliserons sera OpenJFX.
```bash
https://openjfx.io/

```
Téléchargez l’archive de JavaFX nécessaire à votre OS sur le lien et désarchivez-la dans un dossier de votre choix.

```bash
https://gluonhq.com/products/javafx/

```
## Mode de déploiement sur IntelliJ IDEA

Pour exécuter ce projet sur IntelliJ IDEA : 

1. Importer le projet JavaFX

2. Définir le JDK 21

```bash
Accédez à Fichier -> Structure du projet -> Projet et définissez le SDK du projet sur 21. 
```
Vous pouvez également définir le niveau sur 11 ou plus.

3. Créez une bibliothèque
```bash
Accédez à Fichier -> Structure du projet -> Bibliothèques et ajoutez le SDK JavaFX 21 en tant que bibliothèque au projet. 
Pointez sur le dossier lib du SDK JavaFX.
```
Une fois la bibliothèque appliquée, les classes JavaFX seront reconnues par l'IDE.

4. Ajouter des options de VM Pour résoudre le problème

```bash
cliquez sur Exécuter -> Modifier les configurations... et ajoutez ces options de VM : 

Linux / Max :

--module-path /path/to/javafx-sdk-21.0.2/lib 
--add-modules javafx.controls,javafx.fxml

Windows :

--module-path "\path\to\javafx-sdk-21.0.2\lib" 
--add-modules javafx.controls,javafx.fxml
```
Notez que le projet par défaut créé par IntelliJ utilise FXML,donc javafx.fxml est requis avec javafx.controls. 

Si votre projet utilise d'autres modules, vous devrez également les ajouter.


## Mode de déploiement sur Eclipse IDE
Pour exécuter ce projet sur Eclipse

Ouvrez Eclipse et importer le projet Java Qawale Application

Pour compiler et exécuter vos programmes JavaFX dans Eclipse, vous devez d’abord déclarer une nouvelle bibliothèque Java qui contiendra les différents fichiers jar de FX. Pour cela :

```bash
Aller dans Window → Preferences → Dérouler l’onglet Java → Dérouler l’onglet Build Path → cliquer sur User Librairies.

Cliquer sur le bouton New... à droite et renseigner le nom de la nouvelle bibliothèque JavaFX en suffixant par la version téléchargée. 

Cliquer sur le bouton OK.

Sélectionner la bibliothèque et cliquer sur le bouton Add External Jars... à droite.

Aller dans Window → Preferences → Dérouler l’onglet Java → Dérouler l’onglet Build Path → cliquer sur User Librairies.

Sélectionner tous les fichiers jar se trouvant dans le sous-dossier lib de votre dossier d’installation JavaFX
```
Pour ajouter cette bibliothèque au projet Eclipse :

```bash
clic droit sur le projet→ Build Path → Add Librairies...
Choisir User Library → Next >
Cocher la bibliothèque précédemment créée → Finish
```

Lors de l’exécution de ce programme, on peut remarquer l’affichage d’un message d’erreur stipulant qu’il manque des composants d’exécution obligatoire. En effet depuis la version 9 de Java qui introduit un nouveau concept de module, il est nécessaire de préciser à la JVM où trouver les modules et lesquels charger. Dans notre cas il faut charger les modules de JavaFX :
```bash
javafx.controls, javafx.base et javafx.graphics
```

En précisant des options dans la ligne de commande de la JVM :
JavaFX :
```bash
 Dans la vue Package Explorer, clic droit sur la classe main à exécuter → Run As → Run
Configurations ...
```
Dans l’onglet Arguments, renseigner dans le champ VM arguments les deux lignes suivantes :
```bash
--module-path path
--add-modules javafx.base,javafx.controls,javafx.graphics
```
où path représente le chemin de l’installation de JavaFX où se trouvent les fichiers .jar ; ainsi, ce répertoire devra contenir entre autres le fichier javafx.controls.jar, javafx.base.jar
et javafx.graphics.jar. 

L’inconvénient majeur de cette méthode est qu’il faille faire ceci
pour chaque nouvelle classe main que l’on souhaite exécuter.