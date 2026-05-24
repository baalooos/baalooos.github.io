# blog

Blog personnel généré avec [Hugo](https://gohugo.io/) et le thème [Rusty Typewriter](https://github.com/math-queiroz/rusty-typewriter), déployé sur GitHub Pages.

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

Le thème Rusty Typewriter et le module [hugo-notice](https://github.com/martignoni/hugo-notice) sont gérés via Hugo Modules (`go.mod`).

Pour mettre à jour les modules :

```bash
hugo mod get -u
hugo mod tidy
```

## Personnalisation

### Couleur d'accent

Définie dans `assets/css/root.css` via la variable `--primary-color`.

### Page d'accueil

Le texte de biographie et la photo de profil sont configurés dans `data/rtwt/content/home.yaml`.

### Sidebar

Configurée dans `config.yml` sous `params.rtwt.side`.

## Shortcodes

### Justifier du texte

> ⚠️ Les headers `##` à l'intérieur de ce shortcode ne sont pas inclus dans la table des matières.

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

### Notice

```markdown
{{< notice info >}}
Contenu de la notice.
{{< /notice >}}
```

Types disponibles : `info`, `warning`, `tip`, `note`.
