---
layout: section
category: La culture du test
categoryTag: hide
---

# Exploser c'est douter
## Kerbal Space Program

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

Faire décoller une fusée... déjà un bon début

<v-click>

**Revert to launch** : un bouton retour en arrière, sans coût

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
- On retrouve ici l'esprit du **TDD**

<!--
- Le revert to launch permet de tester sans conséquence, à tout moment
- En extrapolant un peu : on retrouve l'essence du TDD → coder, tester, corriger jusqu'à ce que ça passe
- Aparté rapide : la même logique de boucle s'applique quand on pilote un LLM (contexte + critères de test + itération)
-->

---
layout: default
category: La culture du test
---

# Pour les DevOps

- Raccourcir la boucle de **feedback**
- Le **fail fast**, une cible pour votre CI/CD
- Vos devs vous diront merci

<!--
- On lance, ça explose, on recommence... si chaque cycle prend des heures, on ne s'en sort pas
- Fail fast : détecter vite, corriger vite
- Question à se poser en CI/CD : comment apporter rapidement de la valeur à un développeur qui lance des tests ?
-->
