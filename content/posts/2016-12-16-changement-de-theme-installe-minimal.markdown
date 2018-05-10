---
title: 'thème Jekyll : de Minima à Minima...'
date: 2016-12-16 06:00:00 +01:00
categories:
- jekyll
tags:
- jekyll
- github pages
- theme
---

<blockquote class="twitter-tweet" data-lang="fr"><p lang="fr" dir="ltr">Les premiers thèmes pour Jekyll arrivent sur GitHub \\o/ <a href="https://t.co/FiljDMuAc6">https://t.co/FiljDMuAc6</a></p>— Jamstatic-fr (@jamstatic_fr) <a href="https://twitter.com/jamstatic_fr/status/809514418656710658">15 décembre 2016</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

L'annonce est prometteuse. Essayé d'installer le [thème Minimal](https://github.com/pages-themes/minimal) sur un référentiel existant chez Github Pages pour quelques premiers tests en attendant l'arrivée d'autres thèmes de la communauté. Suivi la documentation ce matin...

## la documentation 

Vous aussi, construisez votre site web GitHub Pages avec un thème [Jekyll](https://jekyllrb.com) en quelques clics.

1. Créez un [nouveau référentiel GitHub](https://github.com/new) ou allez sur un référentiel existant.

2. Ouvrez le sélecteur de thème dans la section GitHub Pages "Theme Chooser"  des réglages de votre référentiel.

![Theme-Chooser-Minimal.png](/img/frontend/theme-chooser-minimal.png)

3. Sélectionnez un thème.

![theme-chooser-jekyll.png](/img/frontend/theme-chooser-jekyll.png)

Utiliser un thème Jekyll veut dire que tout votre contenu de site web vit dans des fichiers Markdown, que vous pouvez modifier et gérer comme vous voulez en utilisant votre workflow Git préféré.

Dès que vous appliquez un thème Jekyll à votre site, vous pouvez simplement ajouter d’autres pages en « committant » de nouveaux fichiers Markdown.

Le sélecteur de thème remplace l'ancien générateur automatique de pages qui n'utilisait pas Jekyll. Soyez rassuré, les pages GitHub existantes créées avec le générateur automatique de pages utiliseront automatiquement un thème Jekyll correspondant lors de la première utilisation du sélecteur de thème.

Pour finir, les thèmes Jekyll dans le sélecteur de thèmes sont tous open sourcés [sur GitHub](https://github.com/pages-themes).

Pour bricoler le HTML et la CSS du thème, consultez la [documentation](https://help.github.com/articles/creating-a-github-pages-site-with-the-jekyll-theme-chooser/).

<span id="statut"></span>

## Statut

Très heureux d'avancer tranquillement sous le regard bienveillant de la [communauté de développeurs jamstatic](https://jamstatic.fr/), malheureusement alerté par un e-mail de github, l'installation d'un nouveau thème échoue : 

![email-github-error-build.png](/img/backend/email-github-error-build.png)

### Thème : toujours sur Minima

Bien suivi les instructions pour passer en Minimal. Retour pour voir dans la fenêtre de Terminal. Installation de la gem du thème qui était non trouvée. Le layout posts n'existe pas dans Minimal.

![Erreur-theme-minimal-christopheducamp.github.io — -bash — 135×36 2016-12-16 06-15-50.png](/img/frontend/erreur-theme-minimal.png)

Après résolution de ce bug à faire manuellement et arrêté un choix de thème, je compte bien [personnaliser la CSS et le HTML](https://help.github.com/articles/customizing-css-and-html-in-your-jekyll-theme/) pour quelques premiers raffinages vers l'[indieweb(ification)](http://indiewebify.me).


## Chantier à suivre

* Essayer la documentation du dessus sur un nouveau référentiel
* Étudier comment <span class="h-cite"><cite><span class="u-url p-name">[Créer un thème pour Jekyll](https://jamstatic.fr/2016/10/29/creer-un-theme-pour-jekyll/)</span></cite> - (<a class="p-author h-card" href="https://frank.taillandier.me/">Frank Taillandier</a>, <time class="dt-published">2016-10-29</time>)</span>

## Autres travaux connexes sous le capot

* **UI** Interface de publication : ravi de bosser avec la version développeur gratuite de [siteleaf ](http://siteleaf.com)
* **Langage Liquid** - Localiser la date en francais : trouver une technique plus propre que [mon vieux bricolage](http://christopheducamp.com/2013/12/26/jekyll-localiser-la-date/)
* **SSL** : Certificat SSL effectué chez Gandi à paramétrer proprement pour le faire fonctionner sur ce sous-domaine de famille avec pointage vers GitHub Pages.
