---
title: "Le Bobiverse : les bonnes pratiques de l'IT à l'échelle galactique"
slug: "bobiverse-bonnes-pratiques-it"
author: "Baalooos"
date: 2026-08-10T23:23:59+02:00
tags:
    - "livres"
    - "science-fiction"
    - "exploration spatiale"
    - "espace"
    - "organisation"
    - "pilotage"
    - "produit"
    - "devops"
categories: "Livres"
draft: false
---

{{< justify >}}
Après un premier post sur [Nous sommes Légion \(Nous sommes Bob\)]({{< ref "nous-sommes-legion.md">}}), datant de 2023, j'ai enfin trouvé le temps de me lancer dans une relecture complète pour finir la série. Plutôt que de vous faire un énième post d'analyse et d'avis sur ces romans, j'ai décidé de partir dans une direction un peu différente. Pour rappel, on suit Bob, [une sonde auto-réplicatrice](https://fr.wikipedia.org/wiki/Vaisseaux_spatiaux_auto-r%C3%A9plicateurs) qui se trouve être un ancien développeur de notre époque. Comme nous allons le voir, il va mettre en place des pratiques du monde du développement logiciel et de l'exploitation informatique afin d'affronter les défis auxquels il sera confronté.

## Prise en main d'un système
L'un des premiers réflexes de Bob quand il se retrouve aux commandes de sa sonde est de faire un **audit complet** du système. Grâce à cette précaution, il va découvrir et isoler des mécanismes d'autodestruction mis en place par ses "maîtres". Cette phase de check peut sembler anodine et fastidieuse, pourtant, quand on doit prendre en main un système inconnu, il est nécessaire de faire un état des lieux afin de comprendre les forces et les faiblesses de ce système. Tout comme Bob, identifier et isoler de potentielles failles critiques pourrait bien sauver votre production.

Cette bonne pratique est aussi courante dans le monde des **CTF** ([Capture The Flag](https://fr.wikipedia.org/wiki/Capture_du_drapeau)), des challenges de sécurité informatique où des passionnés doivent attaquer les systèmes de leurs concurrents tout en essayant de protéger les leurs. Cette phase de prise en main va alors permettre deux choses, la détection et le patch de failles critiques sur son propre système, à la fois pour se défendre et pour trouver de nouveaux vecteurs pour attaquer les systèmes adverses. 

En appliquant ici la célèbre devise de Sun Tzu, "Connais ton ennemi et connais-toi toi-même; eussiez-vous cent guerres à soutenir, cent fois vous serez victorieux", Bob illustre bien que la préparation et l'audit peuvent vous sauver la vie, ou à défaut, votre application.

## L'agilité
Une autre bonne pratique que Bob va mettre en place très tôt et qu'il va réutiliser dans presque tous ses projets est l'[agilité](https://agilemanifesto.org/). Il démarre par une V1, **simple** et peu **coûteuse** à mettre en place. Puis, petit à petit, en fonction des retours terrain et de l'augmentation de ses capacités de traitement, il va évoluer vers des solutions de plus en plus complexes et répondant de mieux en mieux à ses besoins. 

Un bon exemple de cette démarche est sa simulation en VR. Afin d'éviter de sombrer dans la folie, Bob recrée un monde virtuel dans lequel il va pouvoir interagir. Son **MVP** (Minimum Viable Product) est très simple: un habitacle peu détaillé mais lui permettant d'avoir une présence "physique". Ensuite, progressivement, il va améliorer les détails, chaque Bob retravaillant certains points en fonction de ses priorités, qu'il s'agisse du goût du café, du réalisme du chat ou du confort du fauteuil de commandement. C'est d'ailleurs un gimmick qu'on retrouve tout au long de la série.

Pour Bob, le mieux est l'ennemi du bien, c'est pourquoi cette approche itérative très utilisée en conception de produit fonctionne si bien. Vous commencez avec les fonctionnalités de base, puis, grâce à une boucle de feedback rapide, vous ajoutez des services jusqu'à obtenir un produit correspondant aux besoins et aux attentes de vos utilisateurs. 

## Toujours avoir une checklist
En complément de cette approche itérative, quand Bob s'attaque à un problème, son premier réflexe est toujours de se poser et de réfléchir. Cette prise de recul tout au long de la série va lui permettre de:

- Faire le tour du problème: essayer de voir plusieurs approches et décider de celle qui lui semble la plus appropriée
- Penser son MVP, pour ensuite définir les étapes de la conception
- Créer une checklist de tâches, à la fois pour le MVP puis pour l'évolution du produit

Comme dans n'importe quel projet, cette checklist va devenir son **backlog** et lui permettra de toujours avoir des tâches en attente. L'un des gros avantages de cette méthode est de pouvoir garder une trace de ce qui lui reste à faire, tout en évacuant de sa mémoire immédiate des problèmes qu'il devra régler plus tard.

Cette liste de tâches lui permet aussi de **prioriser**. C'est une contrainte très positive. En effet, chaque fois qu'il rajoute un item à sa liste, la question se pose de savoir comment le traiter. Est-ce que c'est une urgence, qui prendrait le pas sur tous les autres sujets, ou simplement une idée qui part dans un backlog qui ne sera jamais vidé? 

## L'importance des sauvegardes
Bob va aussi apporter beaucoup de soins à la qualité et à la fréquence de ses sauvegardes. Évidemment, c'est pour lui une question de vie ou de mort. Même s'il est rare que les conséquences soient aussi dramatiques dans notre monde, des études montrent que, sans sauvegarde, une entreprise est condamnée à plus ou moins court terme lorsqu'elle rencontre un incident de production impliquant ses données. Les risques les plus courants restent une attaque par cryptolocking, ou bien simplement le crash d'un serveur de base de données.

L'[incendie d'OVH](https://fr.wikipedia.org/wiki/Incendie_du_centre_de_donn%C3%A9es_d%27OVHcloud_%C3%A0_Strasbourg) en 2021, ou plus récemment [UniSuper](https://www.unisuper.com.au/about-us/media-centre/2024/a-joint-statement-from-unisuper-and-google-cloud) qui voit son compte **GCP** (Google Cloud Platform) supprimé... par GCP lui-même, en sont de bons exemples. La masse de données que l'entreprise accumule au fil du temps est une véritable mine d'or. Dans notre monde où la data est reine, perdre ses données revient à perdre une grande partie de la valeur de l'entreprise. 

Bien conscient qu'en plus de l'importance des sauvegardes, leur fraîcheur est primordiale, Bob va donc mettre en place des sauvegardes **régulières**. En complément, il va aussi réaliser des backups complets avant chaque prise de risques. De la même manière, avant chaque mise en production, il est nécessaire de faire un rapide backup incrémental afin de limiter les pertes de données et de simplifier la procédure de rollback en cas de problème. 

## La résilience
Ancien développeur accompli risquant maintenant ses circuits, Bob sait qu'il doit pouvoir continuer à opérer quoi qu'il arrive. Il est bien conscient aussi que la loi de Murphy n'est jamais loin. Il va donc appliquer les bonnes pratiques de résilience qu'on construit généralement autour de **3 leviers**. Le premier, qu'on a vu au paragraphe précédent, correspond aux sauvegardes. Les 2 suivants sont la redondance et la préparation/l'anticipation des incidents. Pour réussir à rester en vie, Bob va mettre en application ces 3 leviers comme on le ferait dans une entreprise. Il va devoir jongler entre ses ressources, des deadlines impossibles et des commanditaires changeant tout le temps d'avis. 

Pour la redondance, Bob étant une sonde auto-réplicatrice, son objectif premier est de se répliquer. Bien que ça lui pose un problème moral, le Bobiverse grandit quand même à vue d’œil. Multiplier le nombre de réplicas est un procédé bien connu pour améliorer aussi bien la résilience que la tenue en charge d'une application. On peut dire qu'aujourd'hui un outil comme [Kubernetes](https://kubernetes.io/) gère extrêmement bien ça et les options managées proposées par les différents cloud providers permettent de grandement limiter les coûts d'exploitation. 

Pour ce qui est de la préparation et de l'anticipation, Bob va toujours s'imposer d'avoir un plan B. Au début de son aventure, il a bien conscience d'être un être unique. Il doit donc assurer sa survie avant tout, ce qui l'oblige à toujours imaginer les pires scénarios et comment s'en prémunir. Il s'appuie donc sur plusieurs mécanismes bien connus des équipes d'exploitation comme les plans de reprise d'activité et les exercices en conditions réelles pour s'assurer qu'il est toujours prêt à tout. 

Tout comme ces 3 leviers vont assurer la survie de Bob dans un univers vaste et dangereux, ils vont aussi permettre à votre entreprise de prospérer et d'éviter les déboires.

## La gestion des contraintes
Un autre aspect récurrent des aventures de Bob est sa dépendance aux ressources et à sa capacité de production. Le parallèle avec une entreprise, qui doit faire avec ses moyens et ses ressources humaines, est évident.

La première chose qu'il va faire, quand il va chercher à se dupliquer, est de penser en termes de **chemin critique**. Trouver du minerai, créer des imprimantes, créer une station de communication, toutes ces tâches deviennent une routine bien huilée qui va permettre à Bob de coloniser de nouveaux systèmes stellaires. Trouver les tâches les plus critiques et les plus chronophages puis construire un chemin critique est aussi une tâche qu'on retrouve souvent en gestion de projet. 

Bob sera aussi confronté à d'autres problématiques comme faire des choix entre les priorités à court terme des humains et celles à plus long terme de l'humanité. De la même manière, pendant un sprint planning, les devs doivent régulièrement **faire des choix** et décider de quelles tâches réaliser en fonction de contraintes métier ou de contraintes techniques.

Tout comme Bob doit jongler entre ces différentes problématiques, dans votre entreprise les choix que vous faites ont un impact non négligeable sur votre produit, et en fonction de sa maturité ce sera par exemple à vous de choisir entre de nouvelles fonctionnalités ou une amélioration de la stabilité.

## Conclusion
Tout au long de cet article, j'ai choisi de vous montrer avec des exemples concrets comment les Bobs utilisent des pratiques bien réelles du monde du développement et de l'exploitation logicielle pour résoudre des problèmes qui semblent pourtant très éloignés de notre quotidien. C'est une nouvelle approche que je commence seulement à développer et je pense qu'il sera intéressant de voir comment je pourrai m'inspirer de mes lectures pour améliorer mes pratiques au quotidien. Ce sujet sera d'ailleurs au cœur d'un de mes prochains posts, et surtout d'une conférence que je donnerai pour la TechnoZaure de Lyon en septembre 2026.
{{< /justify >}}
