# iTowns Météo
## Description
Ce répertoire **iTowns Météo** constitue un projet qui a été élaboré dans le cadre du module de WebGL, niveau Master 2 TSI 2018/2019 à L’École Nationale des Sciences Géographiques.  
Ce projet permet d’interroger un API créé lors du projet IOT ([YSHMeteoApp](https://gitlab.com/Yassmine.Boudili/yshmeteoapp)) et de récupérer les données météorologiques issues d'un réseau de capteurs (RaspberryPi) à l'École. C'est données sont ensuite affichées en 3D sur le globe terrestre grâce à la librairie iTowns.   

## Utilisation
Pour installer et tester l'application en local, il faut disposer de **Node** et de **npm**.  

 1- Cloner le projet:
```
git clone https://github.com/b-yasmine/itowns-meteo
``` 
2- Installer les dépendances par la commande suivante:   
```
npm install
```  
3- Lancer l'application:  
```
npm start
```  
4- Accéder à la page web via l'adresse indiquée par la commande précédente.  

## Fonctionnalités du projet

**1- Récupérer les positions des capteurs**
On interroge l'API déjà existante et on récupère les positions de tous les capteurs. 
La requête suivante nous permet d'avoir la dernière localisation d'un capteur en particulier (par exemple, de la Raspberry n°10)
```
http://piensg010:3001/last?capteur_type=localisation
```  
Dans le cas où un ou plusieurs capteurs ne sont pas accessibles, on récupère les données de test disponibles sur [json_samples](https://github.com/b-yasmine/itowns-meteo/tree/master/json_samples).  

**2- Afficher des marqueurs**
Sur position récupérée de l'API, on place un marqueur 3D.  
 
![enter image description here](https://raw.githubusercontent.com/b-yasmine/itowns-meteo/master/screenshots/webpage.png)

**3- Récupérer les mesures**
Pour récupérer les mesures, on utilise la même requête citée précédemment en précisant dans les paramètres de la requête la mesure souhaitée (par exemple, la température qui est indiquée par le paramètre "temp").
```
http://piensg010:3001/last?capteur_type=temp
```  

**4- Afficher les mesures**
Dans une liste déroulante, on peut choisir le type de mesures à afficher. Le résultat de chaque sonde s'affiche sous forme d'un texte 3D au dessus du marqueur correspondant.

En ce qui concerne les données relatives au vent, on affiche la valeur de la vitesse moyenne du vent accompagnée d'une flèche 3D. Cette flèche a pour direction la même direction du vent qu'on a récupéré de l'API.

![enter image description here](https://raw.githubusercontent.com/b-yasmine/itowns-meteo/master/screenshots/wind.png)

<iframe width="560" height="315" src="https://www.youtube.com/embed/MqFS_aytzw0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Auteurs
BOUDILI Yassmine, GHADHAB Hiba et THAALBI Sinda.

24 Février 2019.
