---
layout: section
category: La culture du test
categoryTag: hide
---

# Exploser c'est douter
## Kerbal Space Program (2011)

<div class="text-sm opacity-50 mt-4">
#LaCultureDuTest
</div>

<!--
- Vous venez d'être nommé responsable du programme spatial des petits hommes verts
- Mission : faire décoller une fusée... déjà un bon début
- Sorti en 2011 (alpha), il faudra attendre la version 1.0 en avril 2015 (Early Access Steam depuis 2013)
-->

---
layout: image-right
image: /images/02-ksp-01.jpg
category: La culture du test
categoryTag: left
class: slide-context
backgroundSize: contain
---

# Contexte

Donc, maintenant que vous êtes responsable de la fusée, va falloir qu'elle décolle

<v-click>

A votre disposition vous allez avoir:

</v-click>

<v-click>

- La possibilité de créer le **vaisseau** de vos rêves

</v-click>


<v-click>

- Un arbre, vous permettant de débloquer de nombreux **composants**

</v-click>

<v-click>

- Le **Revert to launch** : un bouton retour en arrière, sans coût

</v-click>

<v-click>

*On vit bien dans une simulation, non ?*

</v-click>

<!--
- Nouvelle technologie révolutionnaire : le "revert to launch"
- On lance ses tests, si ça ne se passe pas comme prévu, un bouton ramène la simulation à son point de départ
-->

---
layout: default
category: La culture du test
---

# Pour les Devs

- Vous avez besoin d'un env de test à **coût zéro**

<v-click>

- On peut presque parler de **TDD**
    - Red, Green, Refactor

</v-click>

<!--
- Le revert to launch permet de tester sans conséquence, à tout moment
- En extrapolant un peu : on retrouve l'essence du TDD → coder, tester, corriger jusqu'à ce que ça passe
- Red: Je dois faire voler ma fusée
- Green: Je design une fusée qui décolle
- Refactor: la partie qui sort un peu du cadre du jeu
- Aparté rapide : la même logique de boucle s'applique quand on pilote un LLM (contexte + critères de test + itération)
-->

---
layout: default
category: La culture du test
---

# Pour les DevOps

- Raccourcir la boucle de **feedback**
- Le **Fail Fast, Shift Left**, une cible pour votre CI/CD

<v-click>

- Attention aux outils très lourd (SAST, SCA...)
- Vos devs vous diront merci

</v-click>

<!--
- On lance, ça explose, on recommence... si chaque cycle prend des heures, on ne s'en sort pas
- Fail fast + Shift Left : détecter et corriger le plus tôt et le plus vite possible
- Attention : shift left ne veut pas dire empiler des scanners lourds (SAST : analyse statique du code, SCA : analyse des dépendances) à chaque pipeline
- Un fail fast qui marche bien = moins d'attente pour les devs, une bonne raison pour les DevOps d'y investir du temps
-->
