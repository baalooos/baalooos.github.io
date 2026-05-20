# blog

Blog personnel généré avec [Hugo](https://gohugo.io/) et le thème [PaperMod](https://github.com/adityatelange/hugo-PaperMod), déployé sur GitHub Pages.

## Prérequis

- [Hugo extended](https://gohugo.io/installation/) v0.161.1+
- [Go](https://go.dev/dl/) 1.24+

## Installation

```bash
git clone https://github.com/baalooos/baalooos.github.io.git
cd baalooos.github.io
hugo mod download
```

## Développement

```bash
hugo server -D
```

## Thème et modules

Le thème PaperMod et le module [hugo-notice](https://github.com/martignoni/hugo-notice) sont gérés via Hugo Modules (`go.mod`).

Pour mettre à jour les modules :

```bash
hugo mod get -u
hugo mod tidy
```

## Shortcodes

### Justifier du texte

```markdown
{{< justify >}}

Texte à justifier.

{{< /justify >}}
```

### Image à côté du texte

```markdown
{{< side-by-side src="/images/profile.jpg" alt="Description de l'image" >}}

Texte affiché à gauche de l'image.

{{< /side-by-side >}}
```
