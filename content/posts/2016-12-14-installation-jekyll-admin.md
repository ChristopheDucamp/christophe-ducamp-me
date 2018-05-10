---
title: Installation jekyll-admin
date: 2016-12-14 07:53:00 +01:00
tags:
- plugin
- jekyll
- ux
- ui
- cms
---

Pour faciliter l'ajout de nouveaux posts, installé pour essayer un plugin de Jekyll qui se rapproche d'une interface graphique de type CMS afin de publier du contenu et administrer les sites Jekyll :

[https://jekyll.github.io/jekyll-admin/](https://jekyll.github.io/jekyll-admin/)

Un gros progrès comparé à l'ajout manuel de post. Mais pourquoi ne pas avoir intégré par défaut la mise à jour automatique des champs de métadonnées pour les posts ? 

## Ajout de post avec jekyll-admin

Si vous optez pour *jekyll-admin*, pensez à ajouter quelques champs de métadonnées. Dans mon cas et en m'appuyant sur l'exemple du premier post, j'ai donc ajouté au-dessous de la fenêtre de publication les 3 champs de méta-données : 

1. le `layout` avec `post`
2. un champ `date` 
3. un champ `tags`  

Voici à quoi ressemble l'interface-utilisateur de la fenêtre de publication pour ce post : 

{{< figure 
caption="UI publication - Plugin jekyll metadata"
src="/img/ui-stuff/ui-jekyll-admin-2016-12.png"
>}}

## Prochaines étapes 

### Interface-utilisateur pour ajouter des posts 

* [Edit] Work in progress. Séduit par [SiteLeaf](https://www.siteleaf.com/) après avoir essayé quelques alternatives dans l'espoir de trouver une interface-utilisateur conviviale et adaptée aux utilisateurs néophytes. Petit tour rapide sur GitHub/[Prose.io](http://prose.io), [Forestry.io](http://forestry.io) et [Site Leaf](https://www.siteleaf.com/) suite aux recommandations de Frank :  

> Tu peux commencer avec Github/Prose.io, sous Jekyll Siteleaf ou Forestry.io sont très simples d’utilisation, CloudCannon c’est encore le niveau au dessus avec l’édition de régions côté front. Un peu plus technique et plus complet : Contenful ou Prismic.io qui permettent de générer les structures de contenus via un service et génèrent une API pour ses contenus consommable par d’autres services. (Frank Taillandier, [jamstatic](https://jamstatic-fr.slack.com/?redir=%2Farchives%2Fgeneral%2Fp1481708085000019), 2016-12-14)


* Voir le [tableau comparatif des offres d'hébergement statique / CMS](https://docs.google.com/spreadsheets/d/1FuiC29pnWsRemqvQh3UcHAZSkz_3p-pq-5-6m5ZHdzU/edit#gid=0) 

### Autres travaux
 
* Localisé la date en français : trouvé une technique plus propre que [mon vieux bricolage](http://christopheducamp.com/2013/12/26/jekyll-localiser-la-date/)
* Ajouté un certificat SSL sur le sous-domaine avec pointage vers GitHub
* Premier pas vers l'[indiewebfication](https://indiewebify.me/) : connexion web avec l'ajout d'un 'rel=me' 

