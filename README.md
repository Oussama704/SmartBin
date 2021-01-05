# SmartBin 
## INTRODUCTION 
Dans les zones à forte concentration de population, une génération rapide de déchets  conduit très souvent à un débordement des poubelles et à des rues très sales. Notre  solution permet au personnel de collecte de déchets d'être informé des niveaux de  remplissage en temps réel et de recevoir des notifications de débordements de déchets. 
LES COMPOSANTS UTILISEES 

## ARDUINO UNO 
Le système Arduino est conçu d’une plateforme Open Source installée sur une carte  programmée à microcontroleur AVR permettant l’écriture, la compilation et le test d’un  programme. Les cartes et modules Arduino sont conçus avec des entrées/sorties qui  reçoivent des signaux de capteurs ou interrupteurs qui peuvent eux-mêmes commander  des moteurs et éclairages par exemple. 

## HC 06 
Le module Bluetooth HC-06 permet d'établir une liaison Bluetooth (liaison série) entre une carte Arduino et un autre équipement possédant une connexion Bluetooth (Smartphone, tablette, seconde carte Arduino, etc...). Le module HC-06 est un module "esclave" contrairement au module HC-05 qui est "maître". Un module "maître" peut demander à un autre élément Bluetooth de s'appairer avec lui alors qu'un module "esclave" ne peut recevoir que des demandes d'appairage. 
Ces deux modules peuvent être configurés grâce à des commandes AT (ou commandes Hayes).

## Servo moteur 
Un servomoteur est un système qui a pour but de produire un mouvement précis en  réponse à une commande externe, C'est un actionneur (système produisant une action)  qui mélange l'électronique, la mécanique et l'automatique. 

## Buzzer 
Le buzzer est un composant constitué essentiellement d'une lamelle réagissant à l'effet  piézoélectrique. La piézoélectricité est la propriété que possèdent certains minéraux de  se déformer lorsqu'ils sont soumis à un champ électrique. Ce phénomène est réversible ;  si nous déformons ce minéral, il produit de l'énergie électrique. 

## LCD
 
L'afficheur LCD est en particulier une interface visuelle entre un système (projet) et  l'homme (utilisateur). Son rôle est de transmettre les informations utiles d'un système à un  utilisateur. Il affichera donc des données susceptibles d'être exploiter par l'utilisateur  d'un système. 

## Capteur à Ultarson 
Le détecteur HC-SR04 utilise les ultrasons pour déterminer la distance à laquelle se  trouve un objet. Peu importe l'intensité de la lumière, la température ou le type de  matière, le capteur pourra facilement détecter s'il y a un obstacle devant lui. LED 
Une diode électroluminescente, plus connue sous l'appellation Del ou Led (light-emitting  diode), désigne un composant optoélectronique qui permet l'émission de  lumière monochromatique.

## Fonctionnement 
Nous utilisons la relation d = v.t avec "d" pour la distance, "v" pour la vitesse et "t" pour  le temps. On connait la vitesse d'impulsion qui est égale à 10µs. Le son doit effectuer un  aller (en partant du capteur) pour ensuite rebondir sur l'obstacle et revenir à ce point  de départ. Nous diviserons donc son temps par deux. 
La vitesse du son est égale à environ 340 m/s ce qui nous donnes: 
d = 340.t/2 = 170. donc d = t / 0.0058. 
Pour convertir la valeur de la distance en cm, nous utiliserons : d = t /0.58. 
Lorsque le premier ultrason détecte une distance moins de 20 cm qui notifie le système  qu’un utilisateur va utiliser la poubelle donc le système vérifie d’abord si la poubelle est  pleine ou non en basant sur le deuxième ultrason qui vérifie si la distance est plus  longue que 3 centimètres en affichant des messages des réclamation dans le LCD I2C  16x2 en temps réel pour encourager l’utilisateur d’utiliser la poubelle pour mettre les  déchets ainsi que chaque fois une utilisateur veut mettre des déchets dedans mais la  poubelle est pleine, la poubelle affiche un message au utilisateur pour utiliser une autre  poubelle. 
Tout en gardant une liaison directe entre le serveur est la poubelle pour envoyer en  temps réel des messages sur l’état de la poubelle au serveur (pleine ou vide).
