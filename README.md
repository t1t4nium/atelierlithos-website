# Site web Atelier Lithos

Site vitrine pour [Atelier Lithos](https://atelierlithos.fr), construit avec [Jekyll](https://jekyllrb.com).

## Binaires installés sur le système

- [Ruby](https://www.ruby-lang.org) /usr/bin/ruby
- [RubyGems](https://rubygems.org) /usr/bin/gem
- [Bundler](https://bundler.io) /usr/bin/bundle
- [rbenv](https://github.com/rbenv/rbenv) /usr/bin/rbenv

## Prérequis

- Ruby 3.2.6 (via rbenv)
- Jekyll 3.10.0 (via gem)

## Installation

```bash
# Si rbenv n'est pas configuré
export PATH="$HOME/.rbenv/bin:$HOME/.rbenv/shims:$PATH"

# Installer les gems
bundle install
```

## Structure du site

```
atelierlithos-website-jekyll/
├── _bracelets/          # Collection bracelets
├── _pierres/            # Collection pierres
├── _config.yml          # Configuration Jekyll + collections
├── _layouts/            # Templates HTML
├── _includes/           # Composants (nav, footer)
├── css/                 # Styles
├── assets/images/       # Images (perles, bracelets, hero)
├── index.md             # Page d'accueil (permalink /)
├── cgv.md               # Conditions Générales de Vente (permalink /cgv/)
└── confidentialite.md   # Politique de confidentialité (permalink /confidentialite/)
```

## Ajouter un bracelet

Créer `_bracelets/nouveau-bracelet.md` :

```yaml
---
nom: NOUVEAU
slogan: "Votre slogan"
informations_complementaires: "Fermeture mousqueton · Chaîne de réglage"
image: nouvelle-image.jpg
lien_etsy: https://www.etsy.com/fr/shop/atelierlithosbijoux
etiquettes:
  - Onyx mat
  - Apatite bleue
  - Inox
---
```

## Ajouter une pierre

Créer `_pierres/nouvelle-pierre.md` :

```yaml
---
nom: Nouvelle pierre
origine:
  - Pays d'origine
image: perle-nouvelle-pierre.png
---
```

## Construire le site

```bash
export PATH="$HOME/.rbenv/bin:$HOME/.rbenv/shims:$PATH"
bundle exec jekyll build
```

## Déployer

```bash
bundle exec jekyll build
rsync -avz --delete -e "ssh -4" _site/ SECRET_SERVEUR:/var/www/atelierlithos/
```
