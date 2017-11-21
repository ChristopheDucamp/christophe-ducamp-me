---
title: Compresser des Images dans GoHugo"
date: 2017-08-31T08:36:05+02:00
lastmod: 2017-09-02T11:59:05+02:00 
description: "Trucs pour réduire la taille des images afin de gagner en performance."
draft: false
toc: true
categories: ["photo, photoflow"]
tags: [optimisation, images, imagemagick, shortcodes, thumbnails]
images: ["/img/bike/thumbnails/which-way.jpg"] # écrase l'image open-graph du site
--- 

Chantier en cours pour parvenir à trouver une solution facile pour compresser et publier des images sur le web. Prendre un exemple dans la jungle et construire ...

{{< figure 
  src="/img/bike/thumbnails/which-way.jpg"
  caption="which way ?"
  title="La Vie à Black Rock City"
  attr="crédit Antoine Choque" 
  attrlink="https://www.instagram.com/p/BYdWlHLgiiD/?taken-by=antoine.choque" 
>}} 

## Compresser les images et utiliser les miniatures

Premier point, **vérifiez le niveau de compression des images** que vous postez avec votre outil préféré de manipulation d'images. Personnellement, j'utilise Photoshop (pas encore testé Pixelmator ou Gimp), les outils de ligne de commande ImageMagick et je finis avec [ImageOptim](https://imageoptim.com/mac) pour finir le nettoyage des métadonnées inutiles.

Réglez les niveaux de compression de vos fichiers PNG à 9 (sur 9) et vos fichiers JPG à quelque chose entre 70 et 90 (sur 100). Le niveau dépend du contenu de l'image, aussi assurez-vous de le vérifier après la compression.

Après ça, **créez des vignettes de vos images ajustées à la largeur exacte de voter colonne de texte**. Inutile d'insérer une image 2000x1000 dans votre post quand votre colonne fait 600 px de large, non ? Pour y parvenir, j'utilise la commande ImageMagick pour créer des versions réduites des images dans un sous-dossier "thumbnails" : 

```shell    
    # cree un sous-dossier s'il n'existe pas.
    mkdir -p thumbnails
    
    # cree les versions d'images miniatures dans le sous-dossier
    # thumbnails. Les images reduites portent le meme nom mais font 600px de large.
    find . -maxdepth 1 \( -iname \*.png -o -iname \*.jpg \) -exec convert "{}" -scale 600x "thumbnails/{}" \;
```    

Une fois que c'est fait, **utilisez le shortcode `figure`** fourni nativement par Hugo pour insérer les images plus proprement qu'avec le Markdown pur. 
Les images seront affichées comme des vignettes et seront liées à la version originale. 
Un exemple provenant d'un de mes posts :

```html    
{{</* figure 
    src="/images/ring-distance/thumbnails/Circular_buffer.png" 
    link="/images/ring-distance/Circular_buffer.png"
*/>}}
```    

Le shortcode `figure` est très puissant et peut ajouter des titres, légendes et plus encore. Juste un exemple ici, mais [regardez la documentation](https://gohugo.io/extras/shortcodes#figure) pour la liste complète. 

```html
{{</* figure src="/images/ring-distance/thumbnails/Circular_buffer.png" 
    link="/images/ring-distance/Circular_buffer.png"
    alt="anneau circulaire" 
    title="Image 1"
    caption="anneau de type buffer circulaire."
    attr="Source : Wikipedia"
    attrlink="https://en.wikipedia.org/wiki/File:Circular_buffer.svg"
*/>}}
```    



## Crédits et remerciements 

- [Antoine Choque](https://www.instagram.com/antoine.choque/) (photographe à Black Rock City)
- Matjaz : [Make Your Static Website Even Faster](https://matjaz.it/hugo-power-user-make-your-static-website-even-faster/)
- [Doc Hugo sur les shortcodes figure et instagram](https://gohugo.io/content-management/shortcodes/#figure)

[`figure` shortcode]: #figure
[figureelement]: http://html5doctor.com/the-figure-figcaption-elements/ "un article de HTML5 doctor discutant des éléments fig et figcaption."
[Instagram]: https://www.instagram.com/



