---
title: 'Move2Cloud @Scale Partie 3 - Le pilotage'
author: "Baalooos"
date: 2026-08-19T23:04:08+02:00
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
Ce billet est le dernier d'une série de 3 articles qui parlent du Move2Cloud, de ses défis et de son pilotage.
Autres articles de la série:

- [Partie 1 : Les enablers]({{< ref "move2cloud-at-scale-partie1.md" >}})
- [Partie 2 : Les pièges]({{< ref "move2cloud-at-scale-partie2.md" >}})
- Partie 3 : Le pilotage (vous êtes ici)
{{< /notice >}}

{{< justify >}}
## Le pilotage, une boussole dans la tourmente
Vous avez fini de lire les deux premiers articles de cette série, et vous savez ce que vous avez à mettre en place. Vous savez aussi quels pièges éviter. Vous avez maintenant le kit de démarrage du parfait Move2Cloud à l'échelle.

Votre principal défi maintenant va être de suivre l'avancement du projet et d'agir en conséquence. Je vais donc passer en revue les outils à votre disposition et notamment les **KPIs** (Key Performance Indicators), les différents rituels de suivi et les tableaux de bord dont vous aurez besoin. Je donnerai aussi des pistes sur comment gérer les dérives et la communication avec votre hiérarchie. Ce dernier article conclura enfin cette longue série.

## Les indicateurs clés (KPIs)
La mise en place de KPIs est un élément important de votre pilotage. Vous allez vouloir adresser ces indicateurs à deux niveaux différents. Le premier niveau se concentrera sur les KPIs des applications que vous allez migrer. Comme pour une migration cloud classique, ce premier niveau va vous permettre de suivre l'avancement de la migration de chaque application. Le second niveau se concentrera sur les KPIs de votre usine de migration. Ils vont vous permettre de suivre l'avancement de votre Move2Cloud à l'échelle et le niveau de transformation de votre entreprise.

Ces indicateurs peuvent être :

- Techniques, avec le nombre (ou le pourcentage) d'applications migrées ou le taux de disponibilité des applications avant/après
- Financiers, avec les coûts cloud vs les coûts datacenter, les économies réalisées et l'importance du [FinOps](https://www.finops.org/)
- Humains, avec la satisfaction produit, la montée en compétences des équipes, le nombre de formations ou de certifications...

Ce que vous devez retenir, c'est que si vous vous basez uniquement sur le nombre d'applications migrées, vous n'aurez qu'une vue très parcellaire de la situation. Vous devrez aussi prendre en compte les performances des applications, la satisfaction des utilisateurs et faire des comparaisons avant/après pour justifier la réussite de votre projet.

## Les rituels de suivi
Pour maintenir la dynamique d'un projet de cette envergure, il est indispensable de mettre en place des rituels adaptés à chaque niveau de l'organisation. Ces rituels ne doivent pas être vécus comme une contrainte supplémentaire, mais comme un outil au service des équipes. On retrouve nos 2 niveaux de suivi, l'opérationnel côté équipe produit, le stratégique côté usine, auxquels on rajoute un troisième niveau, le collectif, propre à la dynamique d'équipe.

Au niveau opérationnel, des points de synchro une ou deux fois par mois entre les équipes produits et les [Enabling teams](https://teamtopologies.com/key-concepts) détectent rapidement les blocages et proposent des solutions sans perdre de temps. Ces points doivent rester courts et se concentrer sur les frictions, pas sur l'avancement général.

Au niveau stratégique, un **comité de pilotage** mensuel réunissant le management et les responsables du **CCOE** s'assure que le projet reste aligné avec les objectifs de l'organisation. C'est l'occasion de présenter les grandes métriques, de débloquer les sujets qui dépassent le périmètre des équipes techniques, et de maintenir le sponsoring managérial évoqué plus tôt. Le CCOE propose des solutions, et le management décide des actions à réaliser.

Enfin, au niveau collectif, les guildes et communautés de pratiques jouent un rôle clé. Une demi-journée mensuelle où chaque équipe présente ses avancées, ses galères et ses solutions permet de nourrir l'intelligence collective et de maintenir la motivation sur la durée. C'est aussi le bon endroit pour valider ou faire évoluer les standards communs, en impliquant directement ceux qui les utilisent au quotidien.

## Les tableaux de bord et le reporting
Un pilotage pertinent passe par une bonne visibilité sur l'avancement de votre projet. Pour ce faire, vous allez devoir mettre en place des tableaux de bord adaptés à votre organisation. En effet, un dashboard destiné au **CoDir** n'affiche pas les mêmes métriques qu'un dashboard destiné aux équipes techniques. Cette distinction est importante et ce serait une erreur d'essayer de faire du one size fits all.

Un autre point important à prendre en compte est la qualité et la fraîcheur des données. Vous ne pouvez pas piloter un projet sans être confiant dans les données que vous utilisez. Imaginez-vous essayant d'utiliser une boussole n'indiquant pas le nord. Il est donc nécessaire de mettre en place des process garantissant que vos données sont bien récoltées, traitées et sauvegardées.

Pour les dashboards, vous allez avoir besoin de deux axes de lecture. Vous retrouvez ici le même découpage que pour les KPIs : un premier axe, applicatif, qui va mettre l'accent sur des métriques comme le nombre d'applications migrées, le taux de disponibilité, ou encore les performances de vos applications. L'idéal serait de pouvoir comparer ces données avec leurs valeurs avant migration. Le FinOps mérite aussi une attention particulière : le cloud, mal utilisé ou mal configuré, peut être un véritable gouffre financier.

Le second axe, à l'échelle de l'usine et à destination du management du projet, suivra des métriques telles que l'avancement global de la migration, les économies réalisées par rapport à vos datacenters ou encore la satisfaction du métier suite à la migration. Ces dashboards permettront aussi de rassurer vos sponsors et de célébrer vos victoires, ou de justifier les retards, inévitables dans ce genre de projets.

## La gestion des dérives
Votre projet de Move2Cloud @Scale va drifter. C'est une certitude, même en suivant tous mes conseils ou en recrutant des gens l'ayant déjà fait ailleurs, vous aurez des dérives. Mais c'est ce qui rend cette migration intéressante. Vous allez devoir apprendre à détecter ces dérives avant qu'elles ne deviennent des problèmes. Pour ce faire, vous aurez besoin d'être convenablement outillé pour détecter toutes les métriques qui sortent de l'ordinaire (on peut parler ici de **signaux faibles**). Pour être capable de détecter ces signaux, vous allez devoir commencer par définir ce qu'est la normalité et ensuite voir quelles équipes s'en éloignent. Par exemple une équipe qui cesse de contribuer aux modules communs est peut-être en difficulté ou en surcharge de travail.

Une fois ces dérives constatées, il vous reste un défi de taille. Comment réagir ? Votre première réaction pourrait être de serrer la vis, en mettant des projets sous tutelle ou en rajoutant du process. Comme on l'a vu plus tôt, c'est une mauvaise idée car l'excès de contraintes ne permettra probablement pas à vos équipes de revenir dans le droit chemin, les conduisant au contraire dans une spirale infernale. C'est là que vous allez devoir vous appuyer sur vos Enabling teams. Si tout est bien en place, elles devraient avoir la capacité de venir renforcer vos équipes en difficulté afin de les aider à revenir dans le droit chemin sans les brusquer ni leur donner l'impression d'être punies.

Je n'ai malheureusement pas de solution miracle et vous allez devoir vous fier à votre intuition. Les questions que vous voudrez vous poser seront assez diverses :

- Est-ce qu'il faut intervenir ? C'est une question cruciale même si c'est contre-intuitif, parfois les problèmes peuvent se résoudre tout seuls.
- Est-ce que le problème vient de la définition du projet ? Est-ce qu'il faut refaire une phase de discovery car les équipes de devs ne comprennent pas ce que vous attendez d'elles ?
- Est-ce que c'est un problème de personne ? Ce sera rarement le cas, mais ça reste toujours une possibilité.

En fonction des réponses à ces questions, vous aurez alors plusieurs possibilités. Si le problème est "simple", une intervention ponctuelle des Enabling teams suffira, sinon, pour des problèmes plus importants ou impliquant des gros retards, vous voudrez les traiter grâce à un comité de pilotage exceptionnel.

Vous devez garder en tête que la gestion des dérives d'une équipe produit sera un exercice délicat où vous devrez jongler entre votre volonté d'aider l'équipe et ses besoins réels. Faites confiance à vos Enabling teams qui assurent un suivi régulier des produits pour vous aider à bien intervenir.

## La communication ascendante
Comme je l'ai abordé plus tôt, le sponsoring de la direction est primordial pour la réussite de votre Move2Cloud @Scale. Toutefois, même s'il est nécessaire pour lancer le projet, vous devez vous assurer qu'il persiste sur le long terme, notamment grâce à une communication ascendante. Cette pratique consiste à être capable de faire remonter aux différentes strates de management les informations dont elles ont besoin. Vous devez donc apprendre comment parler le langage du business et de la direction en mettant en avant des éléments concrets. N'hésitez pas à mettre l'accent sur les réductions de coûts, l'amélioration de la disponibilité des applications et de la satisfaction des utilisateurs. Parler le même langage que vos sponsors va permettre de les impliquer sur le long terme en leur montrant qu'ils ont fait le bon choix.

Un autre point crucial est la transparence vis-à-vis de votre management. Tout comme vous attendez d'un responsable d'application qu'il vous prévienne s'il prend du retard, vous devez aussi communiquer avec votre management avant que les problèmes ne deviennent trop critiques. Vos supérieurs vous pardonneront un retard annoncé, beaucoup moins une vérité cachée jusqu'à ce qu'il soit trop tard. Savoir communiquer les problèmes à votre direction est une compétence nécessaire pour garder sa confiance et éviter que le projet ne soit annulé pour de mauvaises raisons. De la même manière, vous devez aussi prendre le temps de célébrer vos succès car même si pour vous, une migration d'application doit devenir la routine, pour votre CoDir, chaque migration réussie est un pas de plus dans la bonne direction.

Ce besoin de remontées d'informations est aussi valable pour vous. Restez à l'écoute des signaux en provenance des équipes produits et des Enabling teams. Le succès de votre migration se jouera souvent sur de petits détails ou des ensembles de signaux faibles détectés à temps.

## Conclusion
Dans ce troisième article, nous avons vu l'importance du pilotage, c'est toujours le cas, mais encore plus pour un chantier de cette envergure. Ce pilotage passe par le suivi des KPIs, par l'intervention auprès des équipes produits et par la communication avec vos sponsors. Avec le changement d'échelle, votre pilotage devra être encore plus fin afin de prévenir les dérives et de garder le cap.

Cet article conclut aussi cette longue série sur le Move2Cloud @Scale. Après avoir vu dans la première partie comment les enablers vous permettent d'augmenter les chances de succès de votre projet, puis dans la seconde comment des pièges, pouvant paraître anodins, peuvent déstabiliser toute votre usine, nous venons de terminer par comment un pilotage rigoureux vous permet de garder la main sur votre migration.

Pour ma part, je trouve qu'intervenir sur des projets pareils est la suite logique de mes plus de dix ans à accompagner des entreprises dans leur Move2Cloud. Ces nouveaux défis me permettent de mettre à profit mes expériences passées, tout en prenant aussi en compte de nouvelles problématiques et en affinant mon accompagnement.
J'espère que cette série vous aidera à y voir plus clair et à vous lancer dans l'aventure. Si jamais vous avez besoin d'accompagnement, n'hésitez pas à me contacter.
{{< /justify >}}
