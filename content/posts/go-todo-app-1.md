---
title: 'Go todo App - Partie 1'
author: "Baalooos"
date: 2025-01-11T23:52:11+01:00
tags: [
    "golang",
    "cli",
    "cobra",
    "sqlite"
]
categories: "Développement"
draft: false
---

{{< justify >}}

En ce début d'année 2025, disposant de plus de temps libre, j'en profite pour approfondir mes compétences en Go à travers plusieurs projets. Pour commencer, voici quelques réflexions sur mon premier programme, un gestionnaire de tâches en ligne de commande.

## Pourquoi Go?

Aujourd'hui Go est un langage incontournable dans l'écosystème cloud-native. Il est au coeur de Kubernetes, Docker ou encore Terraform. Sa simplicité et ses performances en font un langage accessible, facilitant son adoption.
Go est également très adapté à la création d'applications en ligne de commande (CLI), ce qui est un véritable atout pour développer des outils simples et efficaces.
La maîtrise du Go, au même titre que Bash ou Python, permet de se créer un ensemble d'outils pour optimiser et automatiser les tâches courantes.

## Le projet

### Le cahier des charges

Mon application, disponible [ici](https://github.com/baalooos/go-todo-app), se présente sous la forme d'une application en ligne de commande. Je me suis fixé un cahier des charges relativement simple, avec le support des fonctionnalités suivantes:

- Persistance des données sur disque
- Initialisation de l'application avec la création du stockage des données
- Ajout de tâches
- Suppression de tâches
- Affichage de la liste les tâches
- Fonction démo permettant de créer simplement de fausses tâches pour des tests

Nous allons maintenant voir comment le repo Git est organisé.

### Organisation du repository

Le repo est structuré en 3 grandes parties.

- A la racine, on retrouve les fichiers liés à Go ainsi que le README du projet.
- Le dossier _cmd_ qui contient les différentes commandes acceptées par l'application. Par exemple, mon application supporte la commande `go-todo-app list`, on retrouve donc un fichier _list.go_ dans le dossier _cmd_.
- Le dossier _pkg_, qui regroupe des fonctions pouvant être réutilisé dans plusieurs commandes. On y trouve par exemple la fonction _DbConnect_ que nous détaillerons dans la partie dédiée à SQLite.

Ce découpage du repository est standard pour une application en ligne de commande. Ce respect des conventions permet, même à une personne ne connaissant pas encore le projet, une prise en main simplifiée du projet. Cela permet également de contribuer à l'application plus simplement.

## Le stockage des données

La plupart du temps pour ce genre de projet, le stockage des données peut se faire dans un fichier csv, en effet le but est d'avoir un stockage simple. Comme pour moi le but est de me former et de progresser en Go, j'ai décidé de répliquer un cas d'usage réel avec une connexion à une base de données. Pour ne pas ajouter de complexité, et avoir un projet complètement autonome je suis donc parti sur SQLite.

### SQLite

Par sa simplicité et sa fiabilité, SQLite est aujourd'hui l'une des bases de données les plus utilisées au monde. Elle présente aussi un autre avantage, celui d'être complètement autonome. Une base de données SQLite ne nécessite aucun serveur, aucun moteur, il s'agit simplement d'un fichier. Pour plus d'information sur SQLite, vous pouvez consulter [la vidéo d'Olivier Poncet sur le sujet](https://www.youtube.com/watch?v=F1QJwihFs08&t=2s).

### Connexion à la base de données

Go embarque dans la librairie standard ce qu'il faut pour se connecter à une base de données SQL. Pour plus de lisibilité, j'ai créé une fonction dédiée à cette connexion.

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

On peut voir ici qu'on importe le package "database/sql", qui fait parti de la librairie standard et qui va nous permettre d'utiliser la méthode _sql.Open_. Cette méthode nécessite 2 paramètres, un driver et le path vers la base de données.

En me renseignant sur les drivers sqlite3 disponible pour Go, j'ai trouvé de nombreux résultats, c.f. [ce benchmark](https://github.com/cvilsmeier/go-sqlite-bench). Sans connaissance préalable sur le sujet, j'ai choisi [go-sqlite](https://github.com/glebarez/go-sqlite) une implémentation en Go, compatible avec `database/sql`, ayant de bonnes performances et complètement autonome.

Pour le chemin permettant d'accéder à la base de données, comme SQLite utilise un fichier, on lui passe le path vers le fichier utilisé par l'applicatif.

### Conclusion

Dans cette première partie nous avons vu ensemble en quoi le Go est toujours un langage intéressant à étudier, quel était le cahier des charges que je m'étais fixé, l'organisation du repository et comment se connecter à une base de données SQLite en Go.

A bientôt pour, dans une seconde partie, voir comment Cobra va énormément nous simplifier la vie en automatisant une grosse partie de la gestion de la ligne de commande.

{{< /justify >}}
