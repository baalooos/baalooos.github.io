---
title: 'Mes débuts avec Home Assistant'
author: "Baalooos"
date: 2026-05-24T23:27:29+02:00
tags:
    - "home assistant"
    - "zigbee"
    - "WiFi"
    - "chauffage"
    - "plancher chauffant"
    - "raspberry pi"
    - "shelly"
    - "sonoff"
    - "thermostats virtuels"
categories: "Domotique"
draft: false
---

{{< justify >}}
Après notre premier hiver dans la maison, nous nous sommes rendu compte que certaines choses n'allaient pas. Nos consommations électriques étaient très importantes et ce malgré une pompe à chaleur eau/eau réputée très performante. Nous avions beaucoup de mal à avoir une température "normale" dans la maison, soit il faisait beaucoup trop chaud, soit à l'inverse c'était impossible de se réchauffer. Il était donc temps de faire quelque chose. 

## Des débuts chaotiques

A l'époque, j'étais très loin de toute la mouvance home automation, je regardais ça de loin en me disant que ça pourrait être intéressant d'essayer. Quand j'ai eu besoin de revoir le fonctionnement du plancher chauffant, au lieu de vouloir automatiser, je suis resté sur un système à l'ancienne: un thermostat télécommande sans fil, qu'on peut poser dans la maison et qui pilote un contacteur qui va ouvrir ou fermer le plancher chauffant. 

C'est un système assez rudimentaire, mais l'investissement était assez faible et on a donc fait l'essai. Ont suivi plusieurs années de galère à essayer de faire fonctionner correctement le chauffage, la télécommande n'arrivait pas à communiquer avec le contacteur depuis la chambre, les télécommandes perdaient régulièrement la programmation, il n'y avait pas de feedback entre la télécommande et le contacteur donc parfois chauffait pendant des heures, ou à l'inverse ça ne chauffait pas du tout. 
Comme vous l'imaginez, des heures et des heures de perdues à essayer de faire marcher tout ça pour un résultat très moyen et très onéreux. 

## Le passage à Home Assistant

Cette année, avec l'arrivée de mon deuxième enfant, je me suis dit qu'il était grand temps de faire fonctionner tout ça correctement. Je discute donc à gauche à droite, notamment avec mon père qui est passé depuis quelques années au tout connecté, je challenge un peu la solution avec Claude pour m'assurer que ce que j'envisage fonctionne et je peux enfin me lancer dans le projet. 

Fidèle à moi même, le budget n'était pas la priorité et comme bien souvent c'est propice aux débordements. Je vais donc vous détailler comment j'ai commencé à migrer vers une maison connectée en commençant par [Home Assistant](https://www.home-assistant.io/), en parlant ensuite de WiFi et en terminant par Zigbee. 

### Home assistant

Home assistant est open source, gratuit et a pour vocation d'être un point de commande central dans votre maison. Il est capable de parler avec à peu près tout ce qui se fait aujourd'hui et en ajoutant des adaptateurs USB (oui, tout simplement) on peut le rendre compatible Zigbee, Matter... 

Cette versatilité, le côté open source et capable de discuter avec tout le monde en fond un candidat idéal pour mon projet, car une fois le plancher chauffant maîtrisé, j'ai plein d'autres idées de choses que je pourrais automatiser.

J'attrape donc un Raspberry Pi qui traîne (oui celui acheté il y'a 5 ans pour faire des tests avec et jamais vraiment utilisé...) et je lance l'installation. Très pratique, Home Assistant a une [distribution Linux](https://www.home-assistant.io/installation/raspberrypi/), je flash donc ma carte micro SD, et c'est parti. La détection est très simple, il suffit de taper [homeassistant.local](homeassistant.local), et de lancer la première configuration. Je suis branché en filaire donc pas besoin de WiFi.

Le seul achat que j'ai fait, sur les conseils de Claude, c'est une clé USB haut de gamme pour stocker ma base de données, mes logs, mes métriques... Effectivement, une carte micro SD c'est pas le truc le plus solide du monde donc c'est un bon investissement. 

Pour la config je suis parti sur du standard, j'ai ajouté un backup régulier sur la clé USB et une copie vers mon Google Drive en attendant d'investir dans un NAS.

### Le WiFi

Pour le WiFi, il y a deux éléments important à prendre en compte. Le réseau WiFi proprement dit, et les éléments qu'on va ajouter sur le réseau, le WiFi n'étant qu'un des protocoles disponibles. 

Pour mon réseau, je suis chez Free depuis mon passage chez Scaleway et même si c'est pas le plus véloce, j'en suis content. Le principal soucis d'une grande maison, c'est la portée du WiFi. La Freebox fait ce qu'elle peut mais clairement c'est insuffisant. J'ai donc investi dans un kit mesh TP-Link, le [Deco BE25](https://www.tp-link.com/fr/home-networking/deco/deco-be25/). C'est un modèle milieu de gamme, qui gère le WiFi 7 et qui arrive avec deux bornes. Il est évolutif et les gens en sont contents. Le mesh, c'est magique. J'installe tout ça, je branche le primaire à la Freebox, je mets le deuxième dans les combles et on est parti. 

Pour le pilotage de mon plancher chauffant, je suis parti sur des [Shelly 1PM Mini Gen4](https://kb.shelly.cloud/knowledge-base/shelly-1pm-mini-gen4). Le nom peut faire peur, mais en gros ça veut dire qu'ils peuvent piloter une source de courant et que j'ai la consommation en temps réel. Le mini ça va jusqu'à 8A, largement suffisant pour un simple contacteur de plancher chauffer, et le Gen4 ça veut dire qu'ils peuvent fonctionner en WiFi, en Matter ou en Zigbee. 

Dans mon cas, je suis parti sur du WiFi car à ce moment je n'avais pas encore de plateforme Zigbee, c'était donc un moyen simple et efficace de démarrer. En plus, le WiFi me permet aussi de les piloter directement via l'application depuis mon téléphone si jamais je perds Home Assistant. 

Pour les branchements c'est très simple, en plus mes contacteurs sont déjà en 220 donc même pas besoin d'une alim supplémentaire. L'appairage se fait aussi très simplement, ils sont reconnus par Home Assistant via l'intégration Shelly, il ne reste plus qu'à les enregistrer, les renommer et les mettre dans la bonne pièce. 

### Zigbee

Une fois les Shelly installés, j'ai besoin de capteurs de température pour les piloter. J'ai quelques prérequis très simples, je veux du sans fil, avec ou sans écran suivant les pièces et pas trop cher. En me renseignant rapidement, et en demandant à Claude je tombe sur la marque Sonoff qui est spécialisée sur les capteurs, prises, interrupteurs... Zigbee.

Le Zigbee, pour ceux qui comme moi découvrent le sujet, est un protocole de communication sans fil pensé pour des appareils basses consommation comme des réseaux de capteurs. Il existe depuis les années 90 et a une spécification [IEEE 802.15.4](https://en.wikipedia.org/wiki/IEEE_802.15.4) depuis 2004. Le principal avantage est qu'il fonctionne en mesh, ce qui veut dire que chaque appareil du réseau est capable de relayer le signal des autres, ce qui permet d'avoir un réseau très étendu sans matériel spécifique. Dans mon cas, chaque élément Zigbee alimenté en 220V sert de répéteur pour les éléments sur batterie proches de lui, ce qui fait qu'une simple prise connectée branchée en bout de ligne permet d'étendre d'autant la portée du réseau.

Une fois ce choix fait, je commande donc une passerelle USB pour Home Assistant et quelques capteurs. Je sais déjà que pour les chambres je veux que les utilisateurs voient la température qu'il fait, je pars sur des [SONOFF SNZB-02D](https://sonoff.tech/en-fr/products/sonoff-snzb-02d-zigbee-lcd-smart-temperature-humidity-sensor). Discrets, ils peuvent être posés sur un meuble ou fixé au mur et affiche en temps réel la température et le degré d'humidité dans la pièce. Pour la salle de bain en revanche, je commande un [SONOFF SNZB-02P](https://sonoff.tech/en-fr/products/sonoff-zigbee-temperature-and-humidity-sensor-snzb-02p). C'est un capteur aveugle, qui se cache un peu n'importe où.

La passerelle USB s'installe en quelques clics dans Home Assistant, et on peut ensuite très simplement ajouter de nouveaux appareils Zigbee. Encore une fois, le plus compliqué est de bien les nommer, les tagger et de les mettre dans les bonnes pièces. 

### Home Assistant et les thermostats virtuels

Une fois qu'on a un capteur et un actionneur, il nous manque juste un moyen de les faire communiquer entre eux. Même si on pourrait faire ça grâce à des automatisations dans Home Assistant, il existe un élément natif conçu exprès pour ça: le thermostat virtuel.

Le principe est simple, le thermostat peut être éteint ou en mode chauffage, et s'il est en mode chauffage il compare en permanence la température mesurée par le capteurà sa consigne. Si la pièce est trop froide, il active l'actionneur pour lancer le chauffage.

Tout est bien évidemment configurable et pilotable à distance depuis Home Assistant, et on peut aussi simplement avoir l'historique de fonctionnement pour régler tout ça. Le fonctionnement est le même pour un climatiseur, ce qui m'intéressera plus tard (teasing...).

Il ne reste donc plus qu'à créer un thermostat virtuel par zone du plancher chauffant que je veux piloter et on a un chauffage beaucoup plus précis et fonctionnel que l'ancien système à base de télécommande.

## Conclusion

Je vous épargne les détails liés au chauffage, mais comme c'est du plancher chauffant il faut bien évidemment prendre en compte l'inertie. Je travaille encore un peu sur le sujet, mais le résultat est déjà bien meilleur que ce qu'on avait avant. Pour les économies c'est dur à dire, l'hiver ayant été plus doux que les précédents. Tout ce qu'on peut dire pour l'instant c'est qu'on est beaucoup plus efficient, on ne chauffe que quand c'est nécessaire, et on n'a pas eu froid cet hiver.

Concernant Home Assistant, cette première expérience m'a ouvert tout un univers de possibles, que ce soit le pilotage du portail, celui du chauffage de la piscine ou tout simplement de l'éclairage de certaines pièces sans interrupteurs. J'aurai l'occasion d'y revenir dans un prochain article sur comment piloter ses climatiseurs avec un ESP32 et un peu de soudure. 
{{< /justify >}}
