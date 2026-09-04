---
layout: section
category: La gestion des opérations
categoryTag: hide
---

# La prise en main d'un système
## Nous sommes Légion, nous sommes Bob (2016)

<div class="text-sm opacity-50 mt-4">
#LaGestionDesOperations
</div>

<!--
- Bob : un développeur qui meurt dans les années 2010/2020, cryogénisé
- Se réveille un siècle plus tard, téléchargé dans un ordinateur
- Sa mission : intégrer une sonde auto-réplicatrice pour coloniser l'univers, trouver une nouvelle planète pour l'humanité
- Ressuscité par une faction d'extrémistes religieux — pas franchement "le camp du bien"
-->

---
layout: image-right
image: /images/03-bob-01.jpg
category: La gestion des opérations
categoryTag: left
class: slide-context
backgroundSize: contain
---

# Contexte

<v-click>

Bob : un développeur qui meurt dans les années 2010 et est cryogénisé

</v-click>

<v-click>

Se réveille un siècle plus tard, téléchargé dans un **ordinateur**

</v-click>

<v-click>

Doit intégrer une sonde **auto-réplicatrice** pour explorer l'univers

</v-click>

<v-click>

En prenant les commandes de sa sonde, il fait un audit et découvre un **kill switch**

</v-click>

<!--
- Conflits entre gouvernements humains, le centre de Bob est attaqué
- Départ précipité de la Terre à bord de la sonde
- Bob sait que ses "maîtres" ne sont pas les gentils : il audite sa sonde
- Découverte de mécanismes de contrôle, un kill switch permettant de le détruire à distance en cas de désobéissance
- Tout au long de la série, il continuera à auditer et à découvrir de nouvelles choses (pas un audit ponctuel, un processus continu)
-->

---
layout: default
category: La gestion des opérations
---

# La prise en main d'un système...

- Cartographier pour éviter les **zones d'ombres**
- Configuration, **montée en charge**, failover
- Backups, **restauration**

<!--
- Pour Bob, l'audit lui a sauvé la vie ; pour vous, ça sauvera plus probablement la prod en cas d'incident
- La cartographie permet de comprendre le système et de s'assurer que les modifs n'auront pas d'impacts cachés
- Configuration des serveurs, capacité à tenir la charge
- Failover : existe-t-il, comment se comporte-t-il
- Backups : configuration, et surtout procédure de restauration testée
-->

---
layout: default
category: La gestion des opérations
---

# ... et des responsabilités associées

- Appréhender les besoins des utilisateurs, **SLAs**
- Comprendre **l'historique** des décisions (ADR)
- Trouver les bons **interlocuteurs**

<!--
- Besoins réels des utilisateurs, SLA, et cohérence entre la configuration du système et le besoin
- Comprendre l'historique des décisions : pourquoi les choses ont été faites ainsi (pas juste comment elles fonctionnent)
- Savoir qui contacter en cas de problème, qui sont les bons interlocuteurs selon le sujet
-->

---
layout: default
category: La gestion des opérations
---

# Ce qu'on retient

- Un audit est nécessaire à la prise en main d'un système
- Reprendre un système, c'est aussi accompagner les utilisateurs
