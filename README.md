# blog

## Ajout du thème avec git submodule
### Initialisation
```bash
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git submodule update --init --recursive # needed when you reclone your repo (submodules may not get cloned automatically)
```

### Mise à jour
```bash
git submodule update --recursive --remote
```

## Ajout du module Hugo Notice
Source: [Hugo-notice](https://github.com/martignoni/hugo-notice)

Besoin d'avoir golang installé sur le système puis:

```bash
hugo mod init github.com/baalooos/baalooos.github.io
hugo mod get github.com/martignoni/hugo-notice
```

## Macro pour la mise en page
### Justifier du texte
Ajouter ces balises en début et fin de post:
```markdown
{{< justify >}}

{{< /justify >}}
```

### Ajouter une image à côté du texte
Ajouter ces balises avant et après le texte, remplacer le nom de l'image si besoin
```markdown
{{< side-by-side src="/images/profile.jpg" alt="Image de profile" >}}

{{< /side-by-side >}}
```

