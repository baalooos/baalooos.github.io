---
title: 'Move2Cloud @Scale Partie 2 - Les pièges'
author: "Baalooos"
date: 2026-07-26T13:37:55+02:00
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
Ce billet est le second d'une série de 3 articles qui parlent du Move2Cloud, de ses défis et de son pilotage.
Autres articles de la série:

- [Partie 1 : Les enablers]({{< ref "move2cloud-at-scale-partie1.md" >}})
- Partie 2 : Les pièges (vous êtes ici)
- [Partie 3 : Le pilotage]({{< ref "move2cloud-at-scale-partie3.md" >}})
{{< /notice >}}

{{< justify >}}
## Les risques, autant d'obstacles à anticiper
Vous avez fini de lire le premier article de cette série, et maintenant vous maîtrisez les enablers et leurs bénéfices. Avoir une panoplie d'outils à votre service est important, mais vous ne devez pas perdre de vue que mal utilisé, ces outils peuvent devenir des *freins* et provoquer la *frustration*, aussi bien de votre métier que de vos développeurs.

Après avoir longuement parlé des enablers, je vais maintenant me concentrer sur les pièges pouvant mettre en danger votre projet en commençant par des objectifs mal définis et un manque de soutien hiérarchique. Je conclurai cette série par un troisième article qui abordera le pilotage de votre migration et comment éviter les dérives.

### Manquer de Sponsors et de buts bien définis
Un projet de Move2Cloud à l'échelle est un défi important pour votre organisation et vous devez vous assurer de l'adhésion à la fois de votre top management et de vos utilisateurs.

Etre capable de mettre en avant les bénéfices pour vos équipes permettra de réduire la résistance au changement et donnera une image positive du projet. Pour ce faire, vous aurez besoin de faire de la pédagogie auprès de tous les acteurs. Du métier, à qui vous devez expliquer les gains de productivité et de stabilité qu'il va faire; aux équipes techniques pour leur montrer comment cette migration va leur simplifier la vie et leur permettre de reprendre le contrôle du SI.

Arriver à trouver le bon équilibre entre présence du management, conduite du changement et liberté des équipes va être l'un des gros enjeux vous permettant de réussir votre Move2cloud à l'échelle. Afin de maintenir cet équilibre fragile, vous devez garder en tête l'objectif réel de cette migration. Même si votre but est de *moderniser vos applications*, en réalité ce qui va vous permettre d'emporter l'adhésion c'est d'*améliorer la vie de vos utilisateurs*.

> N'oubliez jamais que même si vous avez migré l'intégralité de votre SI vers le cloud, dans un temps record et sans interruption de service, si vos utilisateurs ne sont pas satisfaits, votre migration sera vue comme un échec.

### La gestion de la complexité
Avec les modifications de votre organisation abordées précédemment, il est important de ne pas oublier pourquoi vous travaillez. En effet, vos équipes en charge du SI sont au service du métier et de vos utilisateurs. Quand votre organisation devient trop lourde ou trop complexe, vous commencez à faire face à une *dilution des responsabilités*.

Vous devez donc vous assurer de ne pas avoir trop d'acteurs différents, et de bien définir les rôles et responsabilités de chacun. La multiplicité des acteurs va à la fois diluer les responsabilités et complexifier les processus de décision. Il faut donc que chaque équipe sache précisément ce qu'on attend d'elle, ses domaines de responsabilités, et qui contacter en cas de besoin.

Concrètement, avoir des espaces documentaires affichant un organigramme et les rôles et responsabilités de chaque équipe est un bon début. Vous devrez aussi faciliter la communication entre ces équipes en organisant à la fois des moments de restitution du travail de chacun, et des événements transverses permettant de regrouper tous les acteurs. Vous devez vous donner comme objectifs de supprimer l'opacité. Pour ce faire, vous pouvez vous appuyer sur les rapports d'étonnement des nouveaux venus. Vous devez aussi faire un recueil des irritants, et avoir des gens dont le rôle est de mettre de l'huile dans les rouages.

### Souplesse et standardisation
Même si nous avons vu plus tôt l'importance de la standardisation, il faut faire attention à ne pas tomber dans des modèles trop contraignants qui deviendraient un carcan plutôt qu'une aide pour les équipes. Gardez à l'esprit qu'il est impossible d'avoir un modèle parfaitement standard applicable à toutes les situations. Votre modèle doit prendre en compte ce besoin dès sa conception.

Il est nécessaire, lors de la définition du modèle, de prévoir ce qui est négociable ou non et de documenter les alternatives identifiées en fonction des besoins. Pour prendre un exemple simple, il est obligatoire de faire des sauvegardes, c'est un point non négociable. A l'inverse, le choix du langage de programmation peut être plus libre et dépendre des besoins spécifiques du produit. Dans ce cas, vous devez documenter les différents langages acceptables en fonction des besoins et des compétences à votre disposition.

Un autre risque à ne pas sous-estimer est le *silotage* de vos produits. Chaque équipe doit garder en tête qu'elle travaille à la fois pour son application et pour l'objectif commun: Une migration simple et efficace vers le cloud. Pour atteindre ce résultat, et même si tout semble se passer pour le mieux, il est crucial que vous continuiez à libérer du temps à vos équipes pour contribuer à l'intelligence collective.

Suivant votre organisation et l'appétence de vos équipes, il est possible de faire de la formation interne ou de mettre en place des guildes, rassemblant vos employés en fonction de leurs compétences. Ces moments de partage permettront à vos développeurs de tisser des liens et mettront en avant l'importance de la synergie entre les équipes.

### Maîtriser les enjeux techniques
Au-delà des enjeux culturels sur lesquels j'insiste beaucoup,  ce projet reste un défi technique majeur pour vos équipes. En effet, même si la migration d'un produit devient routinière, le passage à l'échelle présente de gros risques de dérives, aussi bien sur la facture que sur la dette technique.

Sur la partie [FinOps](https://www.finops.org/) tout d'abord, vous devez être conscients que la migration va beaucoup augmenter vos coûts. Même si vous arrivez à standardiser et à mettre en place des bonnes pratiques, tout ne sera pas optimal dès le début. Vous allez devoir jongler entre le besoin de migrer toujours plus d'applications, et le besoin de maîtriser vos coûts. Malheureusement je n'ai pas de recette magique, et vos équipes auront sûrement l'impression de bâtir en avançant mais c'est normal et vous verrez que plus vous migrerez d'applications, plus la moindre optimisation vous apportera des bénéfices importants. Le travail des FinOps n'est pas un one shot, il doit se poursuivre une fois la migration accomplie.

Un autre sujet qui peut dériver très rapidement est la gestion de la dette technique. En effet, vous allez construire votre landing zone et votre innersourcing au fur et à mesure que les produits vous remontent de nouveaux besoins. Arriver à garder tous les projets à jour tout en continuant à progresser et à fournir de nouveaux modules à vos produits sera un vrai challenge pour vos équipes. Heureusement vous pourrez vous appuyer sur des outils comme [Renovate](https://github.com/renovatebot/renovate) afin de suivre ces évolutions dans le temps et avoir une bonne idée de l'accumulation de la dette.

En temps normal, le FinOps et la dette technique sont des sujets importants. Une migration à l'échelle va amplifier encore ces problématiques, vous devez donc être proactifs en permettant à vos équipes d'agir avant qu'il ne soit trop tard.

## Conclusion
Dans ce second article, nous avons vu comment des pièges, d'apparence anodine, peuvent mettre en danger l'ensemble de votre projet. Le manque de sponsors et d'objectifs sont des risques connus en gestion de projet. Mais avec le changement d'échelle, ces risques se retrouvent amplifiés et doivent faire l'objet d'une grande attention. Une fois ces facteurs sous contrôle, vous devrez arriver à gérer la complexité tout en restant souple et en laissant de la liberté à vos équipes. Quand vous en serez là, vous vous rapprocherez du succès. Pour maximiser vos chances, nous verrons dans le 3ème article de cette série comment assurer le pilotage de votre migration: quels indicateurs mettre en place et comment gérer votre reporting afin de rassurer et de convaincre vos sponsors.
{{< /justify >}}
