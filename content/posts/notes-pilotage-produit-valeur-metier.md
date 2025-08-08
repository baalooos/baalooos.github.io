---
title: 'Notes - Pilotage produit par la valeur Metier'
author: "Baalooos"
date: 2025-08-07T15:34:17+02:00
tags: 
    - "pilotage"
    - "produit"
    - "notes"
categories: "Produits"
draft: false
---

{{< justify >}}
## Introduction
Dans le monde du développement produit, il est crucial de comprendre et de définir la valeur métier pour garantir le succès et l'alignement des différentes équipes. Voici donc quelques notes tirées de mes expériences afin de mieux comprendre à quoi ça peut servir.

## Comprendre votre produit
### Définir la valeur métier pour votre produit
Définir ce qu'est la valeur métier pour votre produit dépend largement du produit lui-même et de votre modèle économique. Voici quelques exemples de métriques :

| Domaine      | Métrique                                     |
| ------------ | -------------------------------------------- |
| Marketing    | Nombre de clics sur une bannière             |
| UX           | Pourcentage de tunnels de commande complétés |
| Exploitation | Taux de disponibilité du produit             |
| Aérospatial  | Nombre de fusées envoyées dans l'espace      |

Pour un même produit, les métriques utilisées peuvent varier selon les équipes. Par exemple, pour un site e-commerce, même si la valeur métier reste le nombre de ventes et le chiffre d'affaires, la performance de l'équipe ne sera pas définie de la même manière suivant les équipes:

| Équipe | Métrique de performance |
|--------|-------------------------|
| Exploitants | Taux de disponibilité de l'application et nombre d'incidents |
| Développeurs | Nombre de bugs ou de fonctionnalités livrées |
| UX | Qualité de la navigation sur le site via des questionnaires utilisateurs |

Ces exemples montrent bien que même si le but final reste unique, les moyens d'y parvenir varient énormément suivant l'équipe à laquelle vous appartenez.

## Comment décider ce qu'on va faire ensuite
### Arbitrage entre de nouvelles fonctionnalités et une évolution de l'existant
Lors de la proposition de nouvelles fonctionnalités, l'arbitrage se fait en fonction de plusieurs critères :

| Critère                                                                                |
| -------------------------------------------------------------------------------------- |
| Valeur potentielle de la nouvelle fonctionnalité                                       |
| Valeur prévue pour d'autres nouvelles fonctionnalités déjà prévues                     |
| Valeur prévue pour les évolutions de fonctionnalités existantes                        |
| Gestion de la dette technique, identifiée comme ayant une vraie valeur pour le produit |

### Importance de la valeur métier dans la priorisation du backlog
Lors de la priorisation de votre backlog, il est important d'estimer la valeur métier de chaque fonctionnalité pour prendre une décision éclairée :

| Exemple | Valeur métier |
|---------|---------------|
| Montée de version d'une librairie | Peut sembler inutile, mais si le risque est une indisponibilité ou un risque de sécurité, la valeur métier augmente drastiquement |
| Nouvelle fonctionnalité d'IA | Peut sembler avoir une valeur énorme, mais si le développement est complexe et nécessite de nombreux enablers techniques sans garantie de réussite, la valeur métier peut être jugée moins importante |

Chaque partie prenante doit être capable d'expliquer et de vendre ce sur quoi elle travaille. Ces arbitrages doivent évoluer dans le temps en fonction des retours et des résultats obtenus.

## Penser la surveillance
### Mettre en place des plans de tests
Pour valider des hypothèses à moindre coût, il est essentiel de mettre en place des plans de tests :

| Méthode | Description |
|---------|-------------|
| Partager une idée | Demander du feedback pour améliorer l'idée |
| Tests simples | Utiliser des outils comme Figma ou des mockups pour obtenir des premiers retours sans développer toute la fonctionnalité |
| Key users | Présenter la fonctionnalité à un petit groupe et écouter leurs retours |
| AB testing | Basculer une partie du trafic sur la nouvelle fonctionnalité et observer les différences de comportement |
| Dark launch | Ne pas communiquer sur la fonctionnalité et observer si des utilisateurs l'utilisent naturellement |

### Réfléchir à ce qu'on veut surveiller
Il est important de définir ce qu'on veut surveiller pour valider le fonctionnement d'une fonctionnalité :

| Action                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Voir ce dont on a besoin pour valider le fonctionnement d'une fonctionnalité (analyse comportementale, questionnaires clients, métriques d'utilisation) |
| Vérifier si le monitoring existe déjà                                                                                                                   |
| Définir ce qu'il faut ajouter pour valider une fonctionnalité                                                                                           |

### Mise en place des outils nécessaires
Une fois que l'équipe s'est mise d'accord sur la manière de mesurer le succès d'une fonctionnalité, il faut mettre en place les outils nécessaires. Cette étape est purement technique et dépend beaucoup des outils que vous utilisez. Par exemple, des outils comme Google Analytics pour le suivi des métriques, JIRA pour la gestion des tâches, et des questionnaires en ligne pour recueillir les feedbacks utilisateurs peuvent être utilisés.

## Suivi de l'exploitation
Maintenant que vous savez ce que vous voulez surveiller, et que vous avez mis en place les outils permettant cette surveillance, il vous reste à exploiter ces données. 

### Valider les hypothèses
Comme on l'a vu dans la première partie, certaines fonctionnalités peuvent sembler essentielles. Pourtant à l'usage il arrive régulièrement qu'on se rende compte que ce n'est pas le cas. 

Afin de ne pas prioriser une fonctionnalité moins importante que prévu (voir même complètement inutilisée), il est nécessaire de mettre en place un suivi régulier des indicateurs liés à la valeur métier. 

Ces revues doivent rassembler les différentes parties prenantes et vont vous permettre d'engranger des informations qui seront utiles pour la prochaine phase de priorisation du backlog. 

### Que faire des fonctionnalités n'ayant pas le succès attendu?
Maintenant que l'on connaît notre application, et que l'on est capable de dire quelles fonctionnalités les utilisateurs privilégient, il reste à répondre à une question importante: 
- Quid des fonctionnalités qui ne trouvent pas leur public? 

#### Garder la fonctionnalité
Si une fonctionnalité n'est pas très utilisée, mais qu'elle ne coûte pas grand chose à maintenir, la solution la plus simple reste de la conserver sans investir plus de temps dessus.

Il faut donc flagger cette fonctionnalité pour que tout le monde sache qu'elle est stable, mais qu'à priori elle n'évoluera plus. Et il sera toujours temps plus tard de s'en occuper.

#### Revoir la fonctionnalité
Si une fonctionnalité vous semble importante, mais qu'elle n'est que peu utilisée, vous avez peut-être un problème dans son fonctionnement. 

Grâce à des tests auprès d'un panel d'utilisateurs, il est alors nécessaire de revoir en profondeur son fonctionnement. Dans les pistes potentielles vous avez:
- L'UI/UX de la fonctionnalité, peut-être que la fonctionnalité n'est pas pratique/agréable à utiliser
- L'emplacement de cette fonctionnalité. S'il est nécessaire de faire 10 clics pour arriver dessus, il est peut-être possible de la rendre disponible autrement, d'une manière plus simple
- ...

#### Communiquer sur la fonctionnalité
Les utilisateurs ont besoin de savoir que votre fonctionnalité existe. Il peut donc être nécessaire, grâce à une bannière, de la communication sur les réseaux, une campagne de mailing... de mettre en avant cette fonctionnalité.

#### Supprimer la fonctionnalité
Si malgré tous vos efforts, une fonctionnalité reste sous-exploitée par vos utilisateurs. Alors il est peut-être temps de simplement supprimer cette fonctionnalité. 

Pour cela il faudra accompagner les quelques utilisateurs concernés, prévoir un moyen simple de faire autrement, et passer à autre chose. 

## Conclusion
Voilà, j'espère que ces quelques notes pourront vous aider à mieux comprendre et utiliser la valeur métier.

{{< /justify >}}
