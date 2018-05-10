---
title: "Thème Internet Weblog"
date: "2018-05-10T13:13:17+02:00"
description: "Un nouveau thème pour microbloguer sans titre"
categories: [technologie]
#tags: [gohugo, theme]
slug: ""
aliases: []
toc: false
externalurl: https://themes.gohugo.io/internet-weblog/

---
Changement de thème sur ce *sous-domaine de famille* pour poursuivre mon apprentissage de la motorisation GoHugo. Choisi délibérément le thème [internet weblog](https://themes.gohugo.io/internet-weblog/) créé par [Josh Johnson](https://jnjosh.com/about/) pour son look de blog associant un **flux de microblog** (posts sans titre) et de photoblog. 

`internet-weblog` est un thème Hugo minimaliste (et un peu responsive) offrant notamment la possibilité de faire des liens simples de post reliés à une page distante. (Si vous cliquez sur le titre de ce post, vous êtes envoyé directement sur un lien externe vers ce thème.)

Le thème contient une section bio personnalisable, un flux de photos basé sur flickr dans le pied de page, une mise en page pour afficher tous les posts triés par année et un support pour les partiels afin de personnaliser le style et le javascript.

L'installation se fait classiquement en déclarant le thème dans le fichier `config.toml`.

Pas de difficulté majeure rencontrée sur cette migration si ce n'est comprendre le contrôle de mise en page pour faire apparaître les aperçus de microposts photos. Après avoir francisé les dates, supprimé la justification des textes, plusieurs points restent à régler durant les prochaines semaines. Par ordre de difficulté croissante, ce sera : 

1. l'installation d'un module d'édition avec un lien Github en bas des posts
2. l'[indiewebification](http://indiewebify.me) de l'ensemble
3. la prévisualisation des posts dans Facebook [Protocole Open Graph](http://ogp.me/) cf [discussion](https://discourse.gohugo.io/t/how-to-set-open-graph-image-for-a-specific-page/6700/2)
3. l'ajout de webmentions 
4. l'installation de [flux d'automatisation](https://jnjosh.com/posts/static-blog-automation/) pour publier facilement
4. et le dernier point le plus délicat.... parvenir à installer  d'un point de terminaison micropub fonctionnel pour m'ouvrir le champ de nouvelles interfaces de publication. 