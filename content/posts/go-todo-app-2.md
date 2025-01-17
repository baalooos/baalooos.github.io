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
draft: true
---

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
