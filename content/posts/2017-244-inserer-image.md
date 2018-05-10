---
title: "Insérer des Images dans Hugo"
date: 2017-08-31T17:19:48+02:00
publishDate: 2017-09-01
draft: false
description: "`figure` et `instagram` sont deux shortcodes prédéfinis pour faciliter l'insertion d'images dans un site web motorisé par Hugo."
toc: true
slug: inserer-images
categories: ["technologie"]
tags: [images, instagram, photos]
images: [
  "https://source.unsplash.com/category/technology/1600x900"
] # écrase l'image open-graph valable sur le site
---

Hugo est livré avec un ensemble de *shortcodes* prédéfinis fournis pour la commodité de l'auteur et pour aider à maintenir un contenu markdown propre.

## `figure`

`figure` est une extension de la syntaxe image en markdown, qui ne fournit pas de raccourci pour l'élément plus sémantique  [`<figure>` du HTML5][figureelement].

Le shortcode `figure` peut utiliser les paramètres nommés suivants :

* `src`
* `link`
* `title`
* `caption`
* `class`
* `attr` (pour attribution)
* `attrlink`
* `alt`

### Exemple Input `figure`

```markdown
{{</* figure src="/media/spf13.jpg" title="Steve Francia" */>}}
```


### Exemple Output `figure`

```html
<figure>
  <img src="/media/spf13.jpg"  />
  <figcaption>
      <h4>Steve Francia</h4>
  </figcaption>
</figure>
```

## `instagram`

Si vous souhaitez intégrer une photo provenant d'[Instagram][], vous n'avez besoin que de l'ID de la photo. Vous pouvez retrouver l'ID de photo Instagram à partir de l'URL :

```html
https://www.instagram.com/p/BYdaaQegIB4/
```

### Exemple Input `instagram` 

```go
{{</* instagram BYdaaQegIB4 */>}}
```

Vous avez aussi l'option de cacher la légende :

```go
{{</* instagram BYdaaQegIB4 hidecaption */>}}
```

### Exemple Output `instagram` 

En ajoutant l'exemple précédent `hidecaption`, le HTML suivant sera ajouté à votre marquage de rendu de site web : 


```go
{{< instagram BYdaaQegIB4 hidecaption >}}
```

### Exemple d'Affichage `instagram` 

En utilisant l'exemple précédent `instagram` avec l'exemple `hidecaption` ci-dessus, ce qui suit simule l'expérience affichée pour les visiteurs du site. Naturellement, l'affichage final dépend de vos feuilles de style et des balises environnantes.

{{< instagram BYdaaQegIB4 hidecaption >}}

## Non étudié à cette heure 

- [Chargement Paresseux Intelligent](https://comfusion.github.io/after-dark/#intelligent-lazy-loading) pour optimisation de performances sur le thème GoHugo After-Dark 
- Section [Customizing](https://comfusion.github.io/after-dark/#customizing) de la doc After Dark pour des options supplémentaires.
- [Retailler une image de n'importe quelle taille avec CSS](https://spigotdesign.com/crop-any-size-image-with-css/)
## Références 

- [Doc Hugo sur les shortcodes figure et instagram](https://gohugo.io/content-management/shortcodes/#figure)

[`figure` shortcode]: #figure
[figureelement]: http://html5doctor.com/the-figure-figcaption-elements/ "un article de HTML5 doctor discutant des éléments fig et figcaption."
[Instagram]: https://www.instagram.com/
