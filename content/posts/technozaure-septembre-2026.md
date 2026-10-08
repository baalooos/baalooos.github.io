---
title: 'Technozaure Septembre 2026 - Aliens, IAs et incidents de prod'
author: "Baalooos"
date: 2026-10-02T23:04:57+02:00
tags:
    - "livres"
    - "science-fiction"
    - "exploration spatiale"
    - "espace"
    - "organisation"
    - "pilotage"
    - "produit"
    - "devops"
categories: "Conférences"
draft: false
---

{{< justify >}}
## Introduction
En septembre 2026, j'ai eu la chance de présenter un talk à la Technozaure de Lyon, une journée de conférence interne à [Zenika](https://zenika.com/). Quand j'ai présenté le sujet, je n'avais pas trop d'idées et je me suis inspiré de mes notes pour ce blog post : [Le Bobiverse : les bonnes pratiques de l'IT à l'échelle galactique]({{< ref "bobiverse-bonnes-pratiques-it.md" >}}) (oui je recycle).

J'ai généralisé un peu, même si j'adore le Bobiverse, je ne pense pas qu'il soit suffisamment connu pour déplacer les foules et j'ai obtenu plus ou moins cet abstract :

> Les auteurs de science-fiction imaginent des civilisations qui survivent à des millénaires de crises techniques. Nous, on galère à tenir un run book à jour.La SF regorge de scénarios où des ingénieurs — humains ou non — font face aux mêmes défis que nous, mais avec des enjeux à l'échelle galactique. Dans ce talk, on utilisera des exemples tirés de la SF (romans, films, séries) pour revisiter nos pratiques DevOps : ce qu'on fait bien, ce qu'on fait mal, et ce qu'on ferait probablement encore plus mal si on avait un vaisseau à gérer. Dans cette session, nous allons mettre en perspective nos problèmes du quotidien et trouver des idées concrètes pour améliorer nos pratiques.

{{< /justify >}}

{{< notice tip >}}
Les slides de mon talk sont disponibles [https://baalooos.me/talks/](ici)
{{< /notice >}}

{{< justify >}}
Quelques jours plus tard, j'ai reçu une réponse positive, et il a bien fallu trouver des idées. Pour ce faire j'avais déjà quelques pistes, le Bobiverse bien sûr mais aussi Star Trek et son interpénétration avec la SF, Murderbot, une série de roman un peu déjanté ou on suit un bot tire au flanc et bien d'autres. J'ai profité de ce besoin un peu spécial pour tester le modèle Fable, d'Anthropic en le faisant charbonner. L'idée était simple, voir ce que le modèle avait dans le ventre tout en avançant sur la préparation de ma conférence.

Après quelques allers/retours, je me suis retrouvé avec une liste d'une quinzaine d'œuvres allant du roman au jeux-vidéo en passant par des séries TV et des mangas. Clairement Fable est impressionnant, il m'a permis d'affiner (et de rejeter dans certains cas) mes premières idées, tout en m'en proposant des nouvelles très pertinentes qui sont dans ma présentation. Comme j'aime me simplifier la vie, j'ai aussi décidé de lire quelques bouquins, notamment 2 tomes du cycle de la Culture. Le blog post d'aujourd'hui, regroupe donc toutes les notes que j'ai réuni pour préparer ce talk, les pistes que j'ai laissé de côté. Pour plus de clarté, je vais suivre l'ordre des slides.
{{< /justify >}}

{{< notice warning >}}
!!!!! Attention, ces notes tiennent plus du brouillon que d'un article vraiment construit.
{{< /notice >}}

{{< justify >}}
## Introduction

### Star Trek et la Science - Une longue histoire d'amour
J'ai vu il y a longtemps un documentaire sur Star Trek, et comment, après s'être inspiré des recherches scientifiques de l'époque pour donner de la crédibilité à son univers, la série a suscité des vocations pour des générations de futurs scientifiques et ingénieurs. Le documentaire se nommait [How William Shatner Changed the World](https://en.wikipedia.org/wiki/How_William_Shatner_Changed_the_World), on y suit William Shatner interrogeant des scientifiques et des ingénieurs dont les carrières ont directement été influencées par Star Trek. Il y a notamment Marc Rayman, ingénieur en chef de la propulsion au **JPL** (Jet Propulsion Laboratory) et Martin Cooper, l'inventeur du téléphone portable chez Motorola qui explique avoir été inspiré par les communicateurs de Star Trek. C'est une histoire que j'ai toujours beaucoup aimée et même si elle est très certainement romancée, j'ai décidé d'en faire le point de départ de cette présentation. C'est un exemple simple et concret montrant que la SF, quand elle est bien faite, peut servir d'inspiration pour faire des découvertes dans le monde réel.

### Asimov et ses inspirations
Une autre anecdote, que je n'ai mentionné qu'à l'oral vient d'Asimov et de comment il a eu l'idée de Fondation. James Gunn, dans son article de 1998 "Isaac Asimov and Psychohistory", raconte comment Asimov aurait eu l'idée de la psychohistoire. Il s'est inspiré de la théorie cinétique des gaz qui explique qu'il est impossible de prédire la trajectoire d'une seule molécule de gaz, en revanche il est possible de prédire le comportement statistique d'un ensemble quand on en a des milliards. En ajoutant cette idée à sa lecture d'_Histoire du déclin et de la chute de l'Empire romain_ de Gibbon qui met en avant le fait que la chute des grands empires est toujours suivie d'un âge sombre,  et Asimov sort l'histoire de Trantor, un empire galactique sur le point de s'écrouler, et de Seldon, un mathématicien ayant inventé la psychohistoire. Encore une fois, on voit bien comment science et littérature se confonde pour donner de nouvelles idées à des auteurs.

## Gestion de projet

###  Scotty Factor - Star Trek 3 (ou la série Star Trek en général)

#### Contexte
Dans Star Trek ToS, et dans un certain nombre de films le chef ingénieur Scotty se construit une réputation de faiseur de miracle. Régulièrement, il sauvera la mise de l'équipage grâce à des réparations cruciales dans des délais extrêmement courts.

#### Le cas qui nous intéresse
Dans Star Trek 3 en particulier, il y a un échange qui se veut léger ou l'on voit le capitaine Kirk demander à Scotty un délai pour faire une réparation. Scotty lui répond : Normalement je vous annoncerai 8 semaines, mais comme je sais que vous êtes pressé, je peux vous le faire en 2 semaines. Kirk lui demande alors s'il multiplie toujours ses délais par 4 avant de lui répondre, et Scotty répond avec cette phrase malicieuse : "Bien sûr monsieur. Comment pourrais-je garder ma réputation de faiseur de miracle autrement ?"

#### Morale
Cet exemple est bien connu des amateurs de Star Trek, et on parle même de Scotty Factor. Même si je ne vous recommanderai pas de faire ça dans votre vie de tous les jours, cette surestimation pourra vous aider dans des situations où vous manquez de sécurité psychologique, comme par exemple :

- Si vous venez d'arriver sur un nouveau projet, vous ne connaissez pas encore l'équipe et ça vous laisse le temps de vous habituer
- Si vous êtes dans un environnement toxique et que vous voulez éviter les retards ou le fingerpointing. Ça vous permet de limiter la casse, mais ce n'est pas une solution à long terme.

A l'inverse, quand vous vous êtes bien intégré à votre projet et que vous êtes en maîtrise, vous pouvez passer à d'autres méthodes comme la méthode PERT, qui va consister à inclure une marge de sécurité, mais en étant transparent. C'est plus sain que la méthode de Scotty qui elle doit rester cachée.

On peut aussi citer le projet Aristotle (Google). Il s'agit d'une étude menée en interne à partir de 2012 sur plus de 180 équipes afin d'identifier ce qui fait qu'une équipe est performante. Le résultat met en avant la sécurité psychologique comme facteur majeur de réussite. [Liens vers la source originale](https://rework.withgoogle.com/intl/en/guides/understand-team-effectiveness)

#### Sources

- [Extrait Star Trek](https://www.youtube.com/watch?v=t9SVhg6ZENw)
- [Article sur le Scotty Factor](https://medium.com/design-bootcamp/scottys-first-law-how-expectation-management-builds-trust-9a2f7b822136)

## La culture du test

### Kerbal Space Program

#### Contexte
Vous venez d'être nommé responsable du programme spatial des petits hommes verts. Votre mission, faire une fusée capable... de décoller déjà, c'est un bon début. Ensuite vous irez vers l'infini et au-delà. Vous avez accès à une nouvelle technologie révolutionnaire le "revert to launch". Lancez vos tests, si jamais ça ne se passe pas comme prévu, cliquez sur un bouton et la simulation revient à son point de départ. (On vit bien dans une simulation non ?)

#### Morale de l'histoire
Ce qui est génial dans Kerbal Space Program, c'est qu'à tout moment on peut revenir en arrière, changer 2/3 trucs et refaire un essai. On est sur un test à coût 0. En extrapolant un peu, on peut même parler de test-driven development. On code un truc, on lance les tests et on modifie jusqu'à ce que les tests passent. C'est une approche très pragmatique et hands-on du développement qu'on peut aussi utiliser comme guide quand on travaille avec un LLM. On lui donne un contexte, on lui explique comment tester et on lui dit de boucler jusqu'à ce que les tests passent. Un autre point important est de raccourcir au maximum la boucle de feedback. On lance, ça explose, on recommence, et on recommence, et on recommence. Si à chaque fois on doit attendre des heures entre chaque lancement, on ne s'en sort pas. On parle ici de fail fast, et c'est quelque chose qu'on va vouloir retrouver dans nos chaînes de CI/CD. Comment est-ce que je peux rapidement apporter de la valeur à un développeur qui lance des tests ?

## La gestion des opérations

### L'importance de la prise en main d'un système : Nous sommes légions, nous sommes Bob

#### Contexte
Dans cette série de roman, on suit Bob, un développeur qui meurt quelque part dans les années 2010/2020, est congelé et se réveille dans un ordinateur. Sa fonction est d'intégrer une [sonde auto-réplicatrice](https://fr.wikipedia.org/wiki/Vaisseaux_spatiaux_auto-r%C3%A9plicateurs) pour aller coloniser l'univers et trouver une nouvelle planète pour l'humanité.

De nombreux conflits ont "presque" mené l'humanité à sa perte et pas de chance, il a été "ressuscité" par une faction d'extrémistes religieux.

#### Le cas qui nous intéresse
Alors qu'il est encore en train de s'habituer à sa nouvelle "vie", le centre où Bob est installé va faire l'objet d'une attaque, et des conflits entre les divers gouvernements humains vont entraîner son départ précipité de la Terre à bord de sa sonde. Comme Bob a bien compris que le camp l'ayant ressuscité n'était pas le camp du bien, il va faire un audit de sa sonde et découvrir différents mécanismes de contrôle et un kill switch permettant à ses "maîtres" de le détruire à distance si jamais il n'obéissait pas aux ordres. Tout au long de la série, il continuera à faire des audits et découvrir de nouvelles choses.

#### Morale de l'histoire
Quand on prend un main un système existant, il est important de commencer par un audit afin de bien comprendre à quoi on a affaire. Dans le cas de Bob, ça lui a sauvé la vie, mais pour vous, ça vous permettra plus probablement de sauver la prod en cas d'incident. Cette cartographie va aussi vous permettre de comprendre le système et de vous assurer que vos modifications n'auront pas d'impacts cachés. Dans les choses à vérifier vous aller avoir la configuration des serveurs, voir s'ils peuvent tenir la charge. Comment se passe le failover (s'il y en a un), la configuration des backups, comment ça se passe pour faire une restauration. Vous aurez aussi besoin de comprendre les besoins réels de vos utilisateurs, voir les SLAs et vous assurer que la configuration du système correspond au besoin.

#### Pour aller plus loin
Mes articles sur cette série:
- [Le Bobiverse : les bonnes pratiques de l'IT à l'échelle galactique]({{< ref "bobiverse-bonnes-pratiques-it.md" >}})
- [Nous Sommes Légion (Nous sommes Bob)]({{< ref "nous-sommes-legion.md" >}})

### Le DR (Disaster Recovery) en mode survie : Seul sur Mars

#### Contexte
Suite à un incident, Marc Watney se réveil seul et abandonné sur Mars. Pour survivre, il va devoir réussir à produire de la nourriture, modifier le matériel existant, utiliser des systèmes de spare... Il va même relancer la sonde Pathfinder, une sonde lancée en 1996 (le film se passe en 2035) afin de communiquer avec la Terre. Et surtout, il va faire tout ça en gardant espoir et en documentant ses aventures.

#### Morale de l'histoire
Ce qui va nous intéresser dans les aventures de Watney c'est sa capacité à faire face à une crise. Plutôt que de s'écrouler et de se dire que tout est perdu, il va faire le choix de continuer à travailler, de relancer la station et de survivre. On peut retrouver la même implication dans une équipe d'Ops qui vient d'apprendre que le DataCenter principal à brûlé, qu'il n'y a pas de DR documenté et qu'il faut relancer la prod. Les équipes vont alors tout mettre en œuvre pour relancer cette prod. On retrouve des backups égarés, on relance des vieux serveurs ou on récupère un PoC dans le Cloud qui avait été abandonné et on croise les doigts pour que ça reparte.

A l'image du champ de patates qui explosent, certains plans ne fonctionneront pas mais il y aura aussi des coups de génie comme l'idée de renvoyer Ares 3 pour récupérer Watney. Pendant ces crises majeures, les silos vont tomber et toutes les équipes vont travailler de concert, comme la NASA, le JPL et même la CNSA (agence spatiale chinoise).

Tout comme Watney fait ses vidéo logs pour garder une trace de ses actions, les équipes vont documenter ce qu'ils font pour garder une trace et qui sait, peut-être qu'un jour cette documentation deviendra la documentation qui faisait défaut lors du crash. Attention à ne pas tomber dans le culte du héros, tout comme dans le film, le sauvetage de Watney est autant le fruit de son courage que du travail colossal abattu par la Terre, relancer une infra ne peut se faire seul, et même si les équipes d'Ops vont être au travail non-stop pendant des jours, il ne faut pas oublier qu'il y a toute une organisation derrière.

#### Pour aller plus loin
J'ai depuis eu l'occasion de lire le livre, et même si le film est très bien, le livre lui met une énorme claque.

### La gestion de l'imprévu à l'échelle galactique : Cycle Fondation, Isaac Asimov

#### Contexte
Dans Fondation, on va suivre Hari Seldon, un mathématicien développant la psychohistoire (une manière de prédire l'avenir à une échelle statistique). Il vit dans un empire galactique et ses calculs mettent en évidence une chose : cet empire va s'effondrer. Il ne sait pas exactement quand, ni comment mais dans les grandes lignes il sait que ça va arriver et qu'une période de chaos et de régression va suivre. Il sait qu'il ne peut pas empêcher ce chaos, par contre ses calculs lui montrent qu'il est possible de réduire cette période de chaos avec un peu de préparation. Il va donc mettre en place un DR lui permettant, il l'espère, de considérablement réduire la période de chaos et le nombre de morts.

#### Le cas qui nous intéresse
Malgré sa préparation et tout ce qu'il aura mis en place (les capsules se débloquant régulièrement, Time Vault), la Fondation qui devait sauver l'humanité va se retrouver confronté à des imprévus. On va avoir l'exemple du Mulet, un mutant doté de super pouvoirs et que Seldon n'avait pas prévu. En effet pour lui c'était impossible qu'un seul être humain puisse avoir un impact à l'échelle galactique.

#### Morale de l'histoire
Même quand on pense avoir des procédures bétons capable de répondre à tout, il y a toujours des imprévus. Une des questions que posent cette série, c'est que faire en cas d'imprévus, ce que Banks dans son cycle de la Culture appellera l'Outside Context Problem (Problème hors contexte). On ne peut pas juste s'arrêter là, il faut aussi être capable d'improviser pour réussir. Et quand on improvise une fois, la suite du plan ne va pas se dérouler exactement comme prévu, ce qui va conduire à encore plus d'improvisation.

Ça vous est forcément arrivé déjà, de suivre une procédure et de vous rendre compte qu'elle n'est plus parfaitement à jour. A ce moment, tout ce qu'il vous reste à faire c'est d'avancer, de résoudre les problèmes un à un, et de tellement vous éloigné du plan initial qu'il n'en reste plus rien. Mais ce n'est pas grave, l'important c'est de vous en sortir et, comme Watney, de documenter ce que vous faites pour que, la prochaine fois, vous soyez mieux armé pour réagir à l'inconnu.

#### Pour aller plus loin (Sujet non présent dans le talk)
Dans Fondation, quand le monde est face à une crise majeure, Hari Seldon a mis en place des contingences permettant de résoudre ce qui deviendra des "Crises Seldon". Ces contingences sont des ficelles scénaristiques jusqu'à ce qu'elles ne fonctionnent plus avec l'apparition du Mulet. En forçant un peu, on peut faire un parallèle avec les runbooks. Ces runbooks vont fonctionner, jusqu'à un certain point. Jusqu'à ce qu'on tombe sur un Outside Context Problem, qui oblige à improviser.

## Gestion de la dette

### Quand la dette devient une religion : Warhammer 40K L'Adeptus Mechanicus

#### Contexte
Pour ceux qui ne connaîtraient pas encore Warhammer 40k, c'est un univers dans lequel tout a déconné. Suite à une guerre avec les IAs (les hommes d'acier), l'humanité a perdu sa connaissance technique depuis 10000 ans (plus ou moins) et l'informatique est devenu, encore plus qu'aujourd'hui, une religion. Vous avez des armées de Technoprêtres qui applique des procédures sans les comprendre, qui chantent des quantiques et font des prières quand ils doivent relancer une machine et qui refusent absolument toute nouveautés (c'est un blasphème puni de mort).

#### Morale de l'histoire
On est tous passé par là, des services IT complètement dépassé qui gèrent du legacy depuis des années sans vraiment comprendre pourquoi il faut faire telle ou telle tâche.

Pour éviter de finir comme le Mechanicus, qui place la procédure au-dessus de la compréhension et qui suit religieusement des vieux runbooks incompréhensibles, vous devez toujours tout documenter, le comment, et aussi (surtout), le pourquoi. Vous devez aussi vous assurer que quand tel DevOps part à la retraite, ou s'en va dans une autre organisation, vous savez reprendre le support de ses applications, de ses serveurs et que vous comprenez sa manière de travailler.

Ça peut sembler évident dit comme ça, mais les choses ne se passent que rarement de manière aussi franche. Vous allez perdre la compréhension d'un petit bout de système, puis un jour vous aurez un incident et vous vous rendrez compte qu'en fait ce système était relié à un autre, documenté nulle part, puis vous verrez que votre prod flambant neuve dont vous êtes très fier a un flux non documenté, repris tel que de l'ancien système parce qu'on a toujours fait comme ça et qui justement a besoin de ce système legacy qui vient de tomber...

#### Pour aller plus loin (Sujet non présent dans le talk)
Juste après ma présentation, quelqu'un (coucou Matthias) est venu me voir pour me dire que les dogmes, ça lui avait fait directement penser à autre chose. Et effectivement, je n'y avais pas pensé mais ça s'applique aussi très bien aux coachs Agile. Détenteurs d'un savoir qu'eux même ne comprennent pas vraiment, gardiens du savoir et maître des rituels. Je ne développerai pas plus ici, mais le parallèle pourrait être intéressant à dérouler dans un article dédié.

## Cyber

### D'où viennent les données que vous utilisez ? - Murderbot

#### Contexte
Le narrateur de l'histoire est un bot de sécurité au service des humains. Pour faire simple, c'est un construct, un hybride mi-organique mi-mécanique piloté par une IA, et disposant de son libre arbitre afin de remplir au mieux les missions qui lui sont confié (Protection, exploration...). Pour éviter les problèmes (Rogue IA), il est piloté par un governor module qui s'assure qu'il respecte ses missions, les instructions des humains et qu'il ne critique pas la corporation.
Dans notre cas, il s'agit d'un bot un peu plus malin que la moyenne et qui a un gros problème, il s'ennuie. Pour tromper son ennuie, il a réussi à pirater son governor module et maintenant il est libre de passer ses journées à faire ce qui l'intéresse vraiment : regarder des télénovelas.

#### Le cas qui nous intéresse
La base dont Murderbot à la charge est pilotée par HubSystem, un système local connecté pqr satellite. C'est précisément ce système qui va être compromis et qui va commencer à donner de mauvaises informations aux employeurs de notre bot, et à partir desquelles ils vont faire des erreurs qui pourraient être mortelles. On parle ici de fausses cartes, de balise de secours détruites ou d'un pilote automatique manquant crasher le hopper de l'équipe.

#### Morale de l'histoire
De plus en plus, les SI d'entreprises sont interfacés avec d'autres SIs, d'autres sources de données. Ce qu'on voit ici, c'est qu'injecter de fausses informations (cartes falsifiées) ou même le simple fait de pouvoir altérer des communications peut avoir des conséquences néfastes. De la même manière, quand vos systèmes d'aide à la décision vont se sourcer sur des données que vous ne maîtrisez pas, comment pouvez être sûr que vous pouvez leur faire confiance ?

En journalisme, il existe un principe, la règle des deux sources. Avant de publier une donnée, on s'assure d'avoir plusieurs sources indépendantes et concordantes. De la même manière, vous ne devriez pas accepter de prendre des décisions cruciales sans avoir plusieurs sources corroborant vos informations.

### L'air Gap - Battlestar Galactica

#### Contexte
On est dans les premières minutes de la série, les cylons attaquent et prennent le contrôle de toute la flotte humaine grâce à une cyber attaque sur le réseau. Toute ? Non, un vaisseau, le Galactica, une antiquité, avec à son bord Adama, son commandant, un vétéran de la première guerre contre les cylons et qui a interdit qu'on raccorde le Galactica au réseau. Car il sait de quoi les cylons sont capables.

#### Morale de l'histoire
Même si je ne vous recommande pas de garder des vieux systèmes en considérant que plus personne ne sait les pirater, ce qui va nous intéresser ici ça va plutôt être la notion d'Air Gap/segmentation réseau. Quand vous avez des applications vraiment trop critiques, la meilleure solution pour les protéger sera de ne pas les relier aux réseaux. Ou au moins de les séparer sur un réseau interne très sécurisé, on parlera ici de défense en profondeur.

Vous avez sûrement déjà vécu ça, c'est le VPN admin ou le bastion SSH qui vont permettre d'accéder à certains systèmes. Ce fonctionnement est assez contraignant mais évitera qu'un attaquant puisse pivoter depuis un serveur exposé sur Internet ou depuis le PC corrompu d'un collaborateur.

D'ailleurs dans la série on a un exemple où Adama blessé, l'un de ses officiers va raccorder une partie des ordinateurs du vaisseau au réseau, et c'est seulement l'utilisation d'un pare feu de fortune qui va éviter leur compromission complète. De la même manière, on ne compte plus les exemples d'entreprises pensant être en sécurité et tombant  à cause d'un humain ayant connecté un ordinateur sécurisé n'importe où.

## Conclusion / Ouverture

### La culture

#### Contexte
Dans son cycle de la culture, Banks représente une utopie dans laquelle les humains n'ont plus besoin de travailler et vivent dans l'opulence à bord d'immenses vaisseaux spatiaux, alors que les IAs s'occupent de tout. C'est une civilisation "idéale" qui réalise un vieux rêve de l'humanité : Ne plus avoir besoin de travailler.

#### Le cas qui nous intéresse
L'ensemble du cycle qui présente le fonctionnement de la culture. Les IAs qui complotent les unes contre les autres sont très présentes dans Excession, le 4ème roman de la série.

#### Morale de l'histoire
Dans cette civilisation utopique, Banks imagine que les IAs sont bienveillantes et se consacre au bonheur de l'humanité. Elles ne sont pas parfaites pour autant, et pour passer le temps elles vont comploter les unes contre les autres. On retrouve plusieurs idées ici, si les machines sont capables de tout gérer, qu'est-ce qu'il reste à l'humanité ?

Banks pense la culture comme une utopie où les humains passent leur temps dans les loisirs, les fêtes et le plaisir. A l'opposé, Matrix imagine un futur ou les humains deviennent des piles électriques alimentant les machines. Nous, nous sommes quelque part entre les deux en train d'essayer de comprendre les bouleversements auxquels nous faisons face. On a vu avec Fondation ce que Banks appelle un problème hors contexte, et les LLMs, dont l'impact n'avait pas vraiment été anticipé pourraient être celui de notre décennie. En effet qu'est-ce qu'on va faire quand les LLMs nous remplaceront entièrement ? Des lead devs pilotant des équipes d'agents ? Des relecteurs de PRs ? Des POs posant des specs et laissant les agents travailler ?

Comme on a pu le voir tout au long de cette présentation, la plupart du temps la réponse n'est pas simplement technique. Il s'agit ici de faire un choix, et de décider ce qu'on va pouvoir faire des gains de productivité annoncés.
{{< /justify >}}
