---
title: 'Move2Cloud @Scale Partie 1 - Les enablers'
author: "Baalooos"
date: 2026-06-17T22:37:55+02:00
tags:
    - "cloud"
    - "aws"
    - "migration"
    - "architecture"
    - "organisation"
    - "pilotage"
    - "produit"
    - "zenika"
    - "finops"
    - "devops"
categories: ["Cloud"]
draft: false
---

---
{{< notice info >}}
Ce billet est le premier d'une série de 3 articles qui parlent du Move2Cloud, de ses défis et de son pilotage.
Autres articles de la série:

- Partie 1 : Les enablers (vous êtes ici)
- [Partie 2 : Les pièges]({{< ref "move2cloud-at-scale-partie2.md" >}})
- [Partie 3 : Le pilotage]({{< ref "move2cloud-at-scale-partie3.md" >}})

{{< /notice >}}

{{< justify >}}
## Introduction
Votre entreprise vient de terminer son premier Move2Cloud. Félicitations, c'est déjà une vraie victoire pour vos équipes. Mais honnêtement, même si c'est très bien, vous savez qu'il vous reste encore de nombreuses applications à migrer. La méthode que vous avez utilisée pour cette première application, à base de tâtonnements et d'apprentissages a fonctionné, mais vous voyez déjà les problèmes pour la faire passer à l'échelle.

C'est le sujet que je souhaite aborder dans cette série. Comment faire en sorte que chaque application ne soit pas juste une migration de plus mais plutôt comment transformer votre organisation afin de lui permettre de devenir une véritable machine à migrer. Il existe de nombreux REX sur la migration d'une application, mais ce qu'il manque souvent c'est le *"Et ensuite?"*. Comment est-ce qu'on industrialise tout ça? Comment transformer cette migration en succès?

Dans cet article, et les deux suivants qui arriveront bientôt, nous allons voir quels leviers vont vous aider à passer à l'échelle, les obstacles à anticiper et comment piloter ce projet sans perdre de vue vos objectifs.

## Les enablers, des leviers pour transformer vos produits
En cherchant à capitaliser sur vos premières migrations vers le cloud, votre organisation va petit à petit débloquer des enablers qui vont lui permettre de passer à l'échelle et d'être de plus en plus efficace. Ces enablers que sont la standardisation, la transformation de votre organisation et le support de votre hiérarchie vont nous servir de base de réflexion pour voir comment développer ces supers pouvoirs dans votre organisation.

### Penser Standard
Les premiers move2cloud de produits peuvent faire peur. Depuis des années, vous entendez parler du cloud comme d'un gouffre financier d'une complexité incroyable. Même s'il ne faut pas minimiser la complexité d'une migration, aujourd'hui c'est quelque chose que nous faisons quotidiennement chez [Zenika](https://blog.zenika.com/) et si vous prenez le temps de migrer en vous faisant accompagner, vous devriez pouvoir éviter les principaux écueils.

Comme le disait déjà Dan McKinley en [2015](https://mcfunley.com/choose-boring-technology), *"Choose boring tech"*. C'est exactement ce que vous voulez réaliser avec l'industrialisation de vos Move2Cloud. Pour ce passage à l'échelle, la bascule d'une application de vos datacenters vers les nuages ne doit plus être un challenge. Vos développeurs doivent donc avoir accès à des architectures, des outils et des pratiques bien maîtrisés. Cette standardisation va leur permettre de faire des REX beaucoup plus percutants et immédiatement applicables. Si par exemple une équipe se rend compte que son architecture présente des bottlenecks, la solution qu'elle va proposer pourra probablement être généralisée pour l'ensemble des applications, et donc apporter un vrai gain en terme de performance.

### Penser collectif
L'un des principaux défis que je rencontre en accompagnant des organisations voulant migrer vers le cloud, c'est la formation des collaborateurs. Pour faciliter le passage à l'échelle de votre organisation, il est nécessaire que vous vous appuyiez sur les personnes ayant déjà une (ou plusieurs) migrations réussies à leur actif. Ces référents vont alors pouvoir transmettre leur savoir aux autres équipes, et être un véritable levier pour votre industrialisation. Changer de produit va également renouveler l'intérêt d'experts, qui sinon pourraient avoir l'impression de tourner en rond, vous êtes donc sur du gagnant gagnant.

En mettant en avant le collectif, vous allez faire des vraies économies d'échelles. En effet, chaque équipe doit, en plus de la migration de son application, avoir pour objectif de contribuer au processus d'industrialisation. Cette contribution passe par le partage et la documentation de modules standards réutilisables par d'autres applications. En plus de mettre en avant les participants, et donc de créer une saine compétition, cette pratique va grandement simplifier l'on-boarding des nouveaux développeurs qui auront déjà de la matière à réutiliser.

> Il faut imaginer qu'au lieu d'avoir 10 équipes de 5 personnes travaillant chacune de leur côté, vous avez une équipe de 50 personnes à mi-temps qui travaille sur votre application

Une fois que toute votre organisation travaille ensemble sur cette base de code commune, vous allez pouvoir dédier une task force qui va avoir la responsabilité d'animer et de contribuer à une politique d'innersourcing.

### L'impact sur votre organisation
Afin de répondre aux challenges de l'industrialisation, vous allez aussi devoir faire évoluer votre organisation. Pour ce faire, en plus des équipes produits, vous allez vouloir mettre en place des squads transverses et polyvalentes. En se basant sur [Team Topologies](https://teamtopologies.com/), je vous conseille de mettre en avant deux types d'équipe, les Enabling teams et les Platform teams.

Les Enabling teams sont là pour épauler vos équipes produits, et faire pour elles des choses qui ne rentreraient pas en temps normal dans leurs priorités. Il y a notamment deux situations concrètes où vous voulez avoir des Enabling teams

* **L'on-boarding de nouveaux collaborateurs**, dans ce cas votre Enabling team va avoir le rôle de coach et va pouvoir faire monter rapidement en compétences les nouveaux arrivants. Elle va aussi aider à démarrer efficacement le projet en aidant à choisir une architecture standard et en expliquant comment le produit va pouvoir en tirer partie.
* **Aider une équipe dans le rush**, que ce soit avant l'ouverture de l'application ou pour une mise en prod importante. Comme l'architecture sur laquelle se base l'équipe produit est standard, vos Enabling teams peuvent très simplement arriver et comprendre comment aider sans impacter l'équipe produit.

Vous voudrez aussi mettre en place une Platform Team. En prenant en charge les sujets bas niveaux, elle va avoir pour mission de simplifier la vie des équipes produits. Il peut s'agir par exemple du déploiement des couches réseaux de votre Cloud ou de la mise en place de votre Organisation (au sens AWS).

### La mise en place d'un CCOE
Un bon exemple de Platform team est le CCOE ([Cloud Center of Excellence](https://aws.amazon.com/blogs/enterprise-strategy/designing-a-cloud-center-of-excellence-ccoe/)). Ce concept est apparu autour de 2014/2015 chez AWS, et a ensuite été adopté par les différents acteurs du marché. Malgré cette dizaine d'années d'existence, le CCOE reste un enabler majeur pour tout passage à l'échelle d'une migration vers le cloud. Il s'agit d'un ensemble d'équipes qui vont porter les couches basses de votre Cloud, mais également être garantes de la communication et du respect des bonnes pratiques tout en promouvant l'industrialisation. Ces différentes équipes doivent avoir des responsabilités claires, et on peut les découper par exemple en:

* **Core team**: Responsable de l'orga (au sens AWS) et des briques communes (Direct Connect, TGW...). Cette équipe se compose d'experts du cloud que vous avez choisi et va construire toutes les briques sur lesquelles vont s'appuyer les équipes produits.
* **Cyber Team**: Garante du respect de la PSSI, accompagne les produits, fait de la veille... Le cloud présente de nouveau enjeux de sécurité, et c'est cette équipe qui va s'assurer que vos collaborateurs sont bien conscients des problématiques, tout en mettant en place des outils garantissant que le niveau d'exigence attendu est respecté.
* **Dev/Ops Advocate Team**: Garante de la transmission et du respect des bonnes pratiques. Cette équipe va devoir convaincre et former vos équipes produit. Elle peut aussi animer des guildes ou des communautés de pratiques au sein de votre organisation.
* **Dev Tools Team**: Responsable de l'IDP ([Internal Developer Platform](https://glossary.cncf.io/platform-engineering/)) qui est un enabler important lors du passage à l'échelle, mais aussi de vos Gitlab, Confluence, Wiki, runners, artifactory, ... Cette équipe est là pour répondre aux besoins de vos équipes produit en terme d'outillage, en effet le bon outillage est crucial pour l'industrialisation.
* **FinOps Team** : Garante à la fois de la transmission de bonnes pratiques [FinOps](https://www.finops.org/), mais aussi du bon respect des budgets pour éviter les mauvaises surprises. L'équipe FinOps est là pour vous faire faire des économies intelligemment.
* ...

### Appui hiérarchique et conduite du changement
L'un des critères déterminant la réussite d'un Move2cloud est le sponsoring de la hiérarchie. Ce critère se révèle encore plus important lors du passage à l'échelle. En effet, **si la bascule d'une application est un sprint, migrer l'ensemble du parc d'un gros client est un marathon**. Vous devez donc impliquer le management le plus tôt possible et lui expliquer clairement ce que vous attendez de lui.

En mettant en avant l'importance du Move2Cloud pour votre organisation, vos responsables vont grandement augmenter vos chances de succès. En challengeant le métier, ils vont faire de place pour votre migration dans des roadmaps déjà bien chargées. Le sponsoring du management va aussi vous permettre de convaincre vos équipes techniques de l'importance du projet et du besoin de formation des équipes. Il s'agit par exemple de trouver des budgets de formation, d'être capable de recruter des coachs...

Une fois ce sponsoring garanti, vous devez mettre en place des processus de conduite et d'accompagnement du changement. La migration et la modernisation des applications métiers vers le cloud est l'occasion de revoir et d'améliorer les pratiques des utilisateurs. Afin de garantir une bonne adoption et de diminuer au maximum la résistance naturelle au changement, vous devez faire appel à des coachs. Leur mission sera de comprendre les problématiques métiers et de guider les équipes produits dans la définition des nouvelles applications. Ils devront aussi accompagner les utilisateurs dans la prise en main des nouveaux outils.

## Conclusion
Dans ce premier article, nous avons vu comment des **enablers**, bien utilisés, vous permettent d'augmenter les chances de succès de votre bascule vers le cloud. Parmi eux, la standardisation, le collectif et la mise en place d'Enabling teams sont des enjeux importants de votre migration. Une fois ces bonnes pratiques en place, vous devrez aussi vous appuyer sur votre hiérarchie pour qu'elle vous accompagne et fasse passer les bons messages au métier. Tous ces éléments sont nécessaires à la réussite de votre projet mais ne garantissent en rien son succès. Un tel projet de Move2Cloud @Scale présente de nombreux pièges, et nous verrons dans le prochain article de cette série comment les éviter.

{{< /justify >}}
