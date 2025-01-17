---
title: 'Go todo App - Partie 1'
author: "Baalooos"
date: 2025-01-11T23:52:11+01:00
tags: [
    "golang",
    "cli",
    "cobra"
]
categories: "Développement"
draft: true
---

Comme j'ai un peu de temps libre en ce début d'année 2025, j'ai décidé d'approfondir mes compétences avec quelques projets en Go. Pour commencer, voici quelques réfléxions sur mon premier projet, un gestionnaire de tâches en ligne de commande.

## Pourquoi Go?

Aujourd'hui Go est incontournable dans l'écosystème cloud-native. Il est au coeur de Kubernetes, Docker ou encore Terraform. C'est un langage simple et performant ce qui le rend très accessible, et a permis son adaptotion. Go est aussi très adapté à la création d'applications CLI, ce qui est un véritable atout quand on veut développer des outils simples et performants.
La maîtrise du Go, au même titre que le Bash ou le Python permet donc de se créer un ensemble d'outils pour optimiser et automatiser les tâches courantes.

## Le projet

### Le cahier des charges

Mon application, disponible [ici](https://github.com/baalooos/go-todo-app) se présente donc sous la forme d'une application en ligne de commande. Je me suis fixé un cahier des charges relativement simples, avec le support des fonctionnalités suivantes:

- Persistance des données sur disque
- Init de l'application avec la création du stockage des données
- Ajout de tâches
- Suppression de tâches
- Lister les tâches
- Une fonction démo, permettant de créer de fausse tâches rapidement pour faire des tests

La première étape consiste donc à choisir comment stocker les données.

### Organisation du repository

Dossier cmd
Dossier pkg


## Le stockage des données

La plupart du temps pour ce genre de projet, le stockage des données peut se faire dans un fichier csv, en effet le but est d'avoir un stockage simple. Comme pour moi le but est de me former et de progresser en Go, j'ai décidé de répliquer un cas d'usage réel avec une connexion à une base de données. Pour ne pas ajouter de complexité, et avoir un projet complètement autonome je suis donc parti sur SQLite.

### SQLite

De part sa simplicité et sa fiabilité, SQLite est aujourd'hui l'une des bases de données les plus utilisées au monde. Elle présente aussi un autre avantage, celui d'être complètement autonome. Une base de données SQLite ne nécessite aucun serveur, aucun moteur, il s'agit simplement d'un fichier. Pour plus d'information sur SQLite, vous pouvez consulter [la vidéo d'Olivier Poncet sur le sujet](https://www.youtube.com/watch?v=F1QJwihFs08&t=2s).

### Connexion à la base de données

Go embarque dans la librairie standard ce qu'il faut pour se connecter à une base de données SQL. Pour plus de lisibilité, j'ai créer une fonction dédiée à cette connexion.

```go
package dbutils

import (
    "log"
    "database/sql"
    _ "github.com/glebarez/go-sqlite"
)

func DbConnect(driver string, path string) *sql.DB {
    db, err := sql.Open(driver, path)
    if err != nil {
        log.Fatal("Error connecting to DB", err)
    }
    return db
}
```

On peut voir ici qu'on importe le package "database/sql", qui fait parti de la librairie standard et qui va nous permettre d'utiliser la méthode Open. Cette méthode nécessite 2 paramètres, un driver et le path vers la base de données.

En se renseignant un peu sur les drivers sqlite3 disponible pour Go, on trouve de nombreux résultats, c.f. [ce benchmark](https://github.com/cvilsmeier/go-sqlite-bench). Sans connaissance préalable sur le sujet, j'ai choisi [go-sqlite](https://github.com/glebarez/go-sqlite) une implémentation en Go, compatible avec `database/sql`, ayant de bonnes performances et complètement autonome.

Pour le path, comme SQLite utilise un fichier, on lui passe le path vers le fichier utilisé par l'applicatif.

## La ligne de commande

Pour créer une application en ligne de commande,

En travaillant sur la CLI d'un de mes anciens employeurs, j'ai eu l'occasion de découvrir [Cobra](https://github.com/spf13/cobra). Pour faire simple, Cobra va permettre de déléguer tout la gestion de la ligne de commande. Parmi les features phares on trouve:

- Possibilité d'ajouter des commandes et des sous-commandes simplement
- Suggestions intelligentes, par exemple `app srver`... did you mean `app server`
- Reconnaissance automatique des flags pour l'aide: `-h`, `--help`
- Possibilité de générer automatiquent des pages man à partir du code.

### Cobra

## tabwriter

## Choses à améliorer
