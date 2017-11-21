---
title: r1d39 - GoHugo et After-Dark
date: 2017-08-31 01:37:00 +01:00
publishdate: 2017-09-01
description: Un thème à recommander aux enfants de hackers
author: tof
tags:
- gohugo
- 100daysofcode
- themes
- afterdak
- flying-toasters
slug: afterdark-pour-hugo
images: [
  /img/gohugo/flying-toasters-css.jpg
]
---
<dfn>After-Dark</dfn> (dans le logiciel) est une série de logiciels économiseur d'écran lancée par Berkeley Systems en 1989 pour le Mac. L'économiseur d'écran le plus connu était l'icônique *Flying Toasters* conçu par [Jack Eastman](https://sleepmode.hetnieuweinstituut.nl/en/jack-eastman).

{{< figure
  src="/img/gohugo/flying-toasters-css.jpg"
  caption="After Dark - Flying Toasters"
  class="lazyload"
  attr="(Design Jack Eastman)"
>}}

(hack-memo à imaginer pour les enfants : [animation css](https://www.bryanbraun.com/2014/03/15/how-i-rebuilt-flying-toasters-using-only-css-animations/) des [grille pains volants](http://www.masswerk.at/flyer/?8,md,clr))

Dans le contexte de mon exploration  des [générateurs de site statique](https://jamstatic.fr/), After-Dark est un thème simple et robuste assemblé par <span class="h-card">[Josh Habdas](https://habd.as/)</span>, nomade numérique à Bali. C'est un thème construit sur [hack.css](https://hackcss.egoist.moe/) et je l'apprécie pour la lisibilité du rendu brut très proche du code markdown. Un thème que je conserverai sans doute dans ce nouveau "tipi numérique" motorisé par <a target="intro" href="https://gohugo.io/">GoHugo</a>.

## Présentation After-Dark

<div class="conteneur">
<img 
  data-sizes="auto" 
  data-src="/img/gohugo/minimal-mac.png"
  alt="After Dark sur Macbook et iPhone"   
  class="lazyload" 
  />
  </div>
 
<p align="center">
  <a href="https://www.npmjs.com/package/after-dark"><img src="https://img.shields.io/npm/dm/after-dark.svg?style=flat-square" alt="NPM téléchargements par mois"></a>
  <a href="https://www.npmjs.com/package/after-dark"><img src="https://img.shields.io/npm/v/after-dark.svg?style=flat-square" alt="dernière version NPM"></a>
  <a href="https://github.com/comfusion/after-dark/blob/master/COPYING"><img src="https://img.shields.io/github/license/comfusion/after-dark.svg?style=flat-square" alt="Projet Licence"></a>
</p>

## Fonctionnalités 

<details>
  <summary style="margin-bottom:1em">
    Cliquez sur la flèche pour voir la liste complète des fonctionnalités
  </summary>
  <table>
    <thead>
      <tr>
        <th>Fonctionnalités</th>
        <th>Résumé</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Simplicité Trompeuse</td>
        <td>After Dark est un <a target="feature" href="http://themes.gohugo.io/">thème Hugo</a>, pouvant constituer un bon point de départ pour les <b>développeurs débutants</b> et assimilés. Il évolue en utilisant la philosophie "Code for today, not for tomorrow" du <abbr title="eXtreme Programming">XP</abbr> et ne comprend que le minimum nécessaire pour créer et faire tourner votre site &ndash; rien de plus.</td>
      </tr>
      <tr>
        <td>Versionnage sémantique</td>
        <td>Les changements prévisibles permettent aux utilisateurs du thème de rester au courant de ce qui se passe. After Dark utilise le <a target="feature" href="http://semver.org/">Versionnage Sémantique</a> et maintient un<a target="feature" href="https://github.com/comfusion/after-dark/blob/master/CHANGELOG.md">CHANGELOG</a> pour consommation facile.</td>
      </tr>
      <tr>
        <td>Design Inclusif</td>
        <td>Optimisé pour mobile, tablette, desktop et navigateurs <kbd>terminal</kbd>.</td>
      </tr>
      <tr>
        <td>Optimisé pour la  Performance</td>
        <td>Contenu de page, favicon et styles<b> se chargent en une requête unique</b> sur toutes les pages. Les ressources externes, si présentes, sont chargées de manière asynchrones et seulement si c'est nécessaire. Ceci fait que les pages sont compressés et permet des <b>chargement de pages ~1 sur la 2G</b> si c'est hébergé sur un <abbr title="Content Delivery Network">CDN</abbr>.</td>
      </tr>
      <tr>
        <td>Vertical Scaling</td>
        <td>After Dark est capable de  générer <b>~1000 pages par seconde</b> grâce à <a target="feature" href="https://gohugo.io/">Hugo</a> et il sera probablement encore plus rapide au fil du temps.</td>
      </tr>
      <tr>
        <td><a href="#open-graph">Open Graph</a></td>
        <td>After Dark fournit un support <a target="feature" href="http://ogp.me/">Open Graph</a>   automatique et configurable.</td>
      </tr>
      <tr>
        <td><a href="#optimisation-recherche">Optimisation Moteur de Recherche</a></td>
        <td>Utilisant le <a target="feature" href="https://moz.com/learn/seo/schema-structured-data">Schema Structured Data</a> et les meta tags, After Dark offre aux crawlers une donnée riche sur la structure du site et le contenu. Aucune configuration requise.</td>
      </tr>
      <tr>
        <td><a href="#personnalisation">Personnalisation</a></td>
        <td>Ajustez en utilisant le <a href="#custom-styles">fichier de personnalisation</a> CSS. Choisissez l'une des <a href="#theme-variants">variantes de thèmes</a>. Mettez <a href="#favicon">votre propre favicon</a>. Tirez avantage des <a target="features" href="https://gohugo.io/templates/blocks">modèles de block</a> pour augmenter rapidement de nouveaux layouts personnalisés. Et utilisez les grilles flexbox <a target="features" href="https://hackcss.egoist.moe/dark.html">hack.css</a> et composants CSS pour ajouter du style à votre site.</td>
      </tr>
      <tr>
        <td><a href="#section-menu">Section Menu</a></td>
        <td>Ajoutez et personnalisez votre navigation globale sur le site. After Dark utilise les <a target="feature" href="https://gohugo.io/extras/menus#section-menu-for-the-lazy-blogger">Sections de Menu pour "le Blogueur Paresseux"</a>, rendant la navigation facile à créer et prévisible à utiliser. Vous ne voulez pas de navigation ? Désactivez-la simplement à partir de votre fichier de configuration du site.</td>
      </tr>
      <tr>
        <td><a href="#intelligent-lazy-loading">Chargement Paresseux Intelligent</a></td>
        <td>Charge paresseusement vos images, iFrames et scripts. After Dark utilise la bibliothèque <a title="feature" href="https://github.com/aFarkas/lazysizes">lazysizes</a>, une librairie JavaScript  zéro-configuration avec le support des images <abbr title="Low Quality Image Placeholders">LQIP</abbr> et responsive.</td>
      </tr>
      <tr>
        <td><a href="#shortcodes">Réutilisation du Contenu</a></td>
        <td>Parfois le markdown n'est pas suffisant pour produire un contenu de page engageant. Pour cette raison, After Dark fournit un certain nombre de shortcodes intégrés pour ajouter des choses comme des éléments de citations, des éléments "figure" chargées-paresseusement et des <a target="feature" href="https://hackcss.egoist.moe/">composants hackcss</a> pour vos posts et pages, parmi lesquels bon nombre d'entre eux peuvent être mixés pour créer des expériences vraiment uniques.</td>
      </tr>
      <tr>
        <td><a href="#related-content">Contenu en Rapport</a></td>
        <td>Met en avant plus de contenu aux visiteurs de votre site. En offrant à vos lecteurs plus de contenus pertinents vous aidera à <b>augmenter le nombre d pages vues</b>, le temps passé sur votre site et la fidélité de vos lecteurs.</td>
      </tr>
      <tr>
        <td><a href="#table-of-contents">Table des  Matières</a></td>
        <td>Aidez les utilisateurs à situer et partager l'information sur votre site. En fournissant une <abbr title="Table des Matières">TDM</abbr>, les utilisateurs passeront moins de temps à scroller pour situer l'information dans les grands documents et ils seront plus à même de faire du <i>lien profond</i> vers une information spécifique sur une page.</td>
      </tr>
      <tr>
        <td>Analytics</td>
        <td>Comprendre et actionner sur le comportement utilisateur en activant Google Analytics. After Dark utilise le <a target="feature" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/">snippet de tracking async</a> pour booster la performance et permettre le préchargement du script.</td>
      </tr>
      <tr>
        <td>Contenu Généré par l'Utilisateur</td>
        <td>Améliore les classements "search" et fournit de l'interactivité pour les utilisateurs avec de l'<abbr title="User Generated Content">UGC</abbr>. Activer les commentaires <a target="feature" href="https://disqus.com/">Disqus</a> pour démarrer.</td>
      </tr>
      <tr>
        <td>Temps de Lecture</td>
        <td>Placer les attentes-utilisateur en haut. After Dark fournit <b>un temps de lecture estimé</b> pour chaque post près du haut de la page. Cette fonctionnalité Hugo est automatique et suppose une vitesse de lecture d'environ 200-250 mots par minute.</td>
      </tr>
      <tr>
        <td><a href="#modification-dating">Modification des Dates</a></td>
        <td>Faites rejaillir le contenu mis à jour aux utilisateurs et crawlers, en leur permettant de comprendre quand un post ou une page a été modifiée pour la dernière fois. Les posts mis à jour récemment seront marqués comme modifiés et visuellement remontés dans les listes chronologiques.</td>
      </tr>
      <tr>
        <td><a href="#syntax-highlighting">Surbrillance de Syntaxe</a></td>
        <td>Partager des fragments de code avec style. After Dark fournit une <b>surbrillance de syntaxe en opt-in</b> avec le support pour les numéros de ligne et des lignes mises en surbrillance.</td>
      </tr>
      <tr>
        <td>Pages de Taxonomie</td>
        <td>Aide les utilisateurs à découvrir le contenu taxonomique. After Dark génére automatiquement la <b>taxonomie et les pages de définitions de taxonomie</b> et les lie dans les lignes du post.</td>
      </tr>
      <tr>
        <td>Signatures des Posts</td>
        <td>Les signatures enrichies des posts  comprennent le nom d'auteur facultatif, le nombre de mots, les liens vers des pages de taxonomie et des métadonnées pour les moteurs de recherche.</td>
      </tr>
      <tr>
        <td>Pagination</td>
        <td>La pagination peut être dure. After Dark simplie la liste de pagination avec l'indication de page.</td>
      </tr>
      <tr>
        <td>Page d'Erreur Animée</td>
        <td>Diminue le taux de rebond quand arrivent les erreurs d'URL. After Dark fournit une <a target="feature" href="https://hackcabin.com/post/after-dark-error-page-redesign/">page 404 engageante</a> avec un arrière-plan animé.</td>
      </tr>
      <tr>
        <td>Accessibilité</td>
        <td>After Dark utilise le balisage sémantique  HTML5 pour fournir une meilleure expérience sur les lecteurs oraux. Il facilite la <b>navigation via clavier</b>.</td>
      </tr>
    </tbody>
  </table>
</details>

## Démo & Tutoriel

Rendez-vous sur [Hack Cabin](https://hackcabin.com) pour un **exemple de production** à partir duquel l'[architecture du site](https://hackcabin.com/post/initial-commit/) peut être recréée en utilisant un  [guide pas-à-pas](https://go.habd.as/zero-to-http-2). Et si vous cherchez des exemples, regardez-en [quelques autres](https://github.com/comfusion/after-dark/wiki) pour inspiration.

## Si vous démarrez 

[Installez Hugo](https://gohugo.io/#action) et [elinks](http://elinks.or.cz/) (si vous n'avez jamais  essayé un navigateur terminal) sur votre machine. Les instructions pour installer les deux en utilisant [Homebrew](https://brew.sh/) sur macOS :

```shell
brew install hugo elinks
```

Puis lancez le script d'installation situé dans `bin/install.sh`, ou collez simplement ça dans un terminal et pressez <kbd>Entrée</kbd> :

```shell
curl -s https://raw.githubusercontent.com/comfusion/after-dark/master/bin/install.sh | sh
```

L'installation devrait être terminée en quelques secondes.

## Personnalisation 

### Section Menu

After Dark utilise la [Section Menu pour Blogueurs Paresseux](https://gohugo.io/extras/menus/#section-menu-for-the-lazy-blogger) d'Hugo pour produire une navigation globale du site si c'est activé.

Pour personnaliser le menu, mettez à jour les réglages dans `config.toml` comme suit :

```toml
[[menu.main]]
  name = "Accueil"
  weight = 1
  identifier = "accueil"
  url = "/"
[[menu.main]]
  name = "Posts"
  weight = 2
  identifier = "post"
  url = "/post/"
```

Ou mettez à jour le menu en utilisant le front matter à partir de vos pages : 

```toml
menu = "main"
weight = 3
```

### Chargement Paresseux Intelligent 

Le chargement paresseux met la priorité sur quand et comment les images et plus encore seront téléchargées, améliorant la performance perçue et réduisant le temps de chargement des pages. Si c'est activé, le chargement paresseux fonctionnera automatiquement. Aucune configuration JavaScript n'est nécessaire.

**Ce qui le rend _Intelligent_ ?** Si aucun contenu en chargement paresseux n'est détecté sur une page quand le site est généré, la fonctionnalité ne sera pas activée et aucun téléchargement supplémentaire ne se produira.

Pour activer le chargement paresseux avec [lazysizes](https://github.com/aFarkas/lazysizes), ajoutez `lazyload` à l'attribut de `class`e de vos images/iframes associé à un attribut `data-src` et/ou `data-srcset` :

```html
<!-- non-responsive -->
<img data-src="image.jpg" class="lazyload">
```


```html
<!-- responsive avec calcul automatique des tailles -->
<img
  data-sizes="auto"
  data-src="image2.jpg"
  data-srcset="image1.jpg 300w, image2.jpg 600w, image3.jpg 900w"
  class="lazyload">
```

```html
<!-- exemple iframe -->
<iframe frameborder="0"
  class="lazyload"
  allowfullscreen
  data-src="//www.youtube.com/embed/ZfV-aYdU4uE">
</iframe>
```

Afin de vous aider à démarrer, After Dark inclut un _Shortcode_ tirant profit de cette fonctionnalité, vous permettant de créer facilement des [éléments `figure` chargés paresseusement](#shortcodes) dans votre contenu markdown.

De l'info complémentaire et des exemples, incluant comment régler et utiliser LQIP (Low-Quality Image Placeholders), sont disponibles sur le repo [lazysizes] sur GitHub.

### Contenu en Rapport 

Valorisez davantage votre contenu auprès de vos   visiteurs. En offrant à vos lecteurs plus de contenus pertinents, vous pouvez augmenter les vues, le temps consacré à votre site et la fidélité du lecteur.

Le contenu connexe contribue au contenu à travers les sections en associant les marqueurs de taxonomie. Si After Dark trouve un contenu connexe, il affichera automatiquement une liste de liens vers ce contenu dans un ordre chronologique inversée en-dessous du sous-titre du contenu de votre publication.

Par défaut, After Dark affiche jusqu'à 7 éléments par titre avec leurs temps de lecture. Vous pouvez limiter le nombre d'éléments affichés en définissant le paramètre facultatif suivant dans la section `[params]` de votre fichier `config.toml` :


```toml
related_content_limit = 5
```

### Table des Matières

Aidez les utilisateurs à localiser et à partager des informations sur votre site. En fournissant une <abbr title="Table des Matières">TDM</abbr>, les utilisateurs passent moins de temps à défiler pour localiser des informations dans des documents plus importants et sont plus susceptibles d'accéder aux informations spécifiques et approfondies sur une page.

Pour générer automatiquement une TDM pour un post basée sur l'[outline de page](https://gsnedders.html5.org/outliner/), ajoutez ce qui suit au front matter de votre post : 

```toml
toc = true
```

Pour cacher la Table des matières, réglez `toc = false`, ou enlevez simplement le réglage sur le front matter du post.

After Dark utlise les éléments HTML5 [`details`](http://devdocs.io/html/element/details) et  [`summary`](http://devdocs.io/html/element/summary) pour fournir une TDM qui ne requiert pas l'usage de CSS ou JavaScript pour fonctionner.

Quand une page est chargée la première fois, la TDM sera repliée, ainsi elle n'encombre pas la page. Une fois étendue, sélectionner un item dans la TDM amènera un défilement tout en douceur vers cette section dans le document, mettra en surbrillance le titre de section et mettra à jour la barre d'endroit du navigateur pour un lien profond et un support du bouton retour.

### Open Graph

After Dark tire profit des tags Open Graph en utilisant le [template interne](https://github.com/spf13/hugo/blob/142558719324aa1628541d556ef1fa2d123f1e68/tpl/tplimpl/template_embedded.go#L159-L201) *non-documenté* pour parvenir à des cartes de partage riches pour Facebook et d'autres réseaux sociaux, comme affiché ici : 

<img 
  data-sizes="auto" 
  data-src="/img/gohugo/feat-social-awareness.png"
  alt="capture-écran carte de partage Open Graph"   
  class="lazyload"
  />

Pour créer une carte de partage social comme celle montrée au-dessus, spécifiez `author` dans `config.toml` et, remplacez-la à partir de votre front matter comme suit :

```yaml
title: Devenez un Nomade Digital à Bali : The Lost Guide
description: Tout ce que vous devez savoir pour devenir un Nomade Digital à Bali.
author: After Dark
date: 2017-02-02T11:57:24+08:00
publishdate: 2017-01-28T02:31:22+08:00
images: [
  https://source.unsplash.com/-09QE4q0ezw/2000x1322
]
```

**Pourquoi utiliser la notation en array pour une image ?** [Le Protocole Open Graph](http://ogp.me) supporte les [arrays](http://ogp.me/#array) et les utilisateurs pourraient vouloir augmenter les templates internes Hugo pour faire ainsi.

Pour configurer les images Open Graph sur tout le site pour utilisation comme ressorts pour les posts qui ne spécifient pas leurs propres images open graph, ajoutez un array d'URLs à la section `[params]` dans le fichier  `config.toml` :

```toml
images = [
  "https://source.unsplash.com/-09QE4q0ezw/2000x1322" # Image par Défaut Open Graph pour le site
]
```

Voir [Source Unsplash](https://source.unsplash.com/) pour les options de configuration d'images.

**Note :** Bien que ce puisse être possible, After Dark ne supporte pas les liens relatifs vers les images. Si vous souhaitez disposer de cette fonctionnalité, [ouvrez une nouvelle issue](https://github.com/comfusion/after-dark/issues/new).

### Optimisation Moteur de Recherche

After Dark est construit avec le SEO en tête. Schéma de Données Structurées et autres meta sont appliqués pour donner aux robots ce qu'ils veulent, automatiquement et sans configuration nécessaire.

Le paramétrage par défaut assure que votre site *Hugo-After-Dark* se classera bien dans les <abbr title="Search Engine Results Pages">SERP</abbr>s et empêchera les crawlers web d'indexer du contenu non désirable. Affinez vos réglages "search" en utilisant les options suivantes disponibles.

#### Vérification Webmaster

Vérifiez votre site avec plusieurs outils de webmaster comme Google, Bing, Alexa et Yandex. Pour autoriser la vérification de votre site avec tout ou partie de de ces fournisseurs, ajoutez ce qui suit à votre `config.toml` et remplissez avec leurs valeurs respectives :

```toml
[params.seo.webmaster_verifications]
  google = "" # Optionnel, Google verification code
  bing = "" # Optionnel, Bing verification code
  alexa = "" # Optionnel, Alexa verification code
  yandex = "" # Optionnel, Yandex verification code
```

**Note :** La revendication de votre site avec Alexa a été [retirée en may 2016](https://support.alexa.com/hc/en-us/articles/219135887-Claiming-has-been-retired-May-2016). Cependant, la vérification Alexa a été ajoutée comme une commodité pour les sites existants 
migrant vers After Dark.

#### Descriptions Meta

Les titres de page bien conçus aident à attirer l'attention sur les pages de résultats de recherche. Et les méta-descriptions fournissent un résumé du contenu et pourquoi il est pertinent pour le lecteur, la conduite des clics.

Afin d'ajouter une description meta à vos pages et posts, ajoutez `description` au front matter :

```toml
description = "Tout ce que vous devez savoir pour devenir un Nomade Digital à Bali."
```

En plus d'apparaître dans les moteurs de recherche, les descriptions meta apparaissent aussi sur les pages individuelles et dans les résumés de contenu, ajoutant de la transparence sur leur façon d'apparaître sur  vos pages dans le "search".

Si aucune description personnalisée n'est fournie, After Dark utilisera la description fournie dans `config.toml`. Apprenez-en plus en lisant [Comment créer vos descriptions meta](https://moz.com/learn/seo/meta-description).

#### Modification de la Date

Aidez les agents utilisateur à savoir quand les posts ont été modifiés pour la dernière fois. Pour faire ainsi, ajoutez `publishdate` au front matter de votre page et mettez à jour `date` à chaque fois que vous faites une mise à jour sur un post.

Les mises à jour seront rendues visibles aux lecteurs en mettant le contenu en haut dans votre page et dans les listes de posts, et en utilisant des appels visibles sur les résumés de contenu. Pour les robots, faire une telle modification provoquera une mise à jour automatique des "Schema Structured Data" et feeds  Web, tout comme le réglage `lastmod` dans votre fichier `sitemap.xml`.

Vous pouvez être spécifique et utiliser un datetime (avec décalage horaire) comme suit : 

```
date = "2017-02-02T01:20:56-06:00"
publishdate = "2016-11-21T10:32:33+08:00"
```

Ou moins spécifique et utiliser simplement les dates : 

```
date = "2017-02-02"
publishdate = "2016-11-21"
```

En plus de `date` et `publishdate`, il est également possible de définir une date de péremption. Les messages expirés disparaîtront automatiquement lorsque le site sera construit, mais le contenu sera conservé. Pour le contenu futur ou passé pour expiration, définissez le champ `expirydate` dans le front matter.

#### Blocage Index

Le fait qu'une page apparaisse dans votre `sitemap.xml` ne signifie pas que vous souhaitez la faire apparaître dans un SERP. Les exemples de pages qui apparaîtront dans votre fichier `sitemap.xml` que vous ne voulez généralement pas indexer par les robots d'exploration incluent les pages d'erreur, les pages de recherche, les pages légales et les pages qui contiennent simplement des résumés d'autres pages.

Bien qu'il soit possible de bloquer l'indexation de la recherche à partir d'un fichier `robots.txt`, After-Dark permet de bloquer l'indexation des pages en utilisant également la configuration Hugo. Par défaut, les types de page suivants seront bloqués :

- Pages Section (par ex. les listes de posts)
- Pages Taxonomie (par ex. les listes de catégories et tags)
- Pages de définitions de taxonomie (par ex. les Pages de listes de taxonomies)

Pour personnaliser le blocage par défaut, configurez le réglage `noindex_kinds` dans la section `[params]` de votre fichier `config.toml`.

Par exemple, si vous voulez activer le crawling pour les sections apparaissant dans [Section Menu](#ajouter-un-menu-section), ajoutez ce qui suit à vore fichier de configuration : 

```
[params]
  noindex_kinds = [
    "taxonomy",
    "taxonomyTerm"
  ]
```

Pour bloquer les pages individuelles de l'indexation, ajoutez `noindex` au front matter de votre page et réglez la valeur sur `true`, comme :

```yaml
noindex: true
```

Et pour finir, si vous utilisez Hugo `v0.18` ou une version plus récente, vous pouvez ajouter un fichier `_index.md` avec le front matter `noindex` afin de contrôler l'indexation des layouts de listes pour les sections spécifiques : 

```shell
├── content
│   ├── modules
│   │   ├── starry-night.md
│   │   └── toilettes-volantes.md
│   └── news
│       ├── _index.md
│       └── retour-flying-toasters.md
```

Pour en savoir plus sur la façon dont les crawlers utilisent cette fonctionnalité, lisez [Bloquer l'indexation de la recherche avec l'instruction "noindex"](https://support.google.com/webmasters/answer/93710).

#### Types de Liens

Pour le contenu contextuel découpé sur plusieurs pages dans une séquence, After Dark supporte l'utilisation des réglages `prev` et `next` dans votre front matter. Utilisez-les pour fournir des relations sémantiques entre les pages dans un article segmenté ou une série ou un [LiveBlogPosting](https://schema.org/LiveBlogPosting).

```yaml
prev: /series/apprendre-a-coder/partie-un/
next: /series/apprendre-a-coder/partie-trois/
```

Les "Link Types" sont communément affichés en haut de la page dans les browsers terminal comme moyens auxiliaires de navigation. Ils peuvent aussi aider les crawlers à mieux comprendre les relations dans votre contenu.

Vous pouvez en savoir plus sur les [link types](http://devdocs.io/html/link_types) et comment  [personnaliser les taxonomies Hugo](https://gohugo.io/taxonomies/overview/).

#### Mots-clé Meta

Les mots-clés meta offrent un détail sémantique aaux crawlers concernant l'importance du sujet de votre contenu. Les mots-clés meta sont générés automatiquement pour les pages avec les tags utilisés pour cette page, et pour les autres pages utilisant la taxonomie des catégories du site. Les mots-clés et phrases-clés peuvent se personnaliser en réglant une array `keywords` dans votre front matter :

```toml
keywords = [
  "transformation digitale"
  "developpement web",
  "digital marketing",
  "social media",
  "link building"
]
```

Bien qu'ils ne soient pas considérés comme pertinents pour certains robots d'indexation, les mots-clés peuvent être utiles pour documenter les termes de recherche cibles à utiliser dans la publicité en ligne <a title="Pay-Per-Click">PPC</abbr> et fournir une valeur sémantique à vos pages.

### Output Markdown

Contrôlez mieux la conversion de markdown en HTML. En modifiant les paramètres du processeur de markdown, vous pouvez profiter des fonctionnalités de [Blackfriday](https://github.com/russross/blackfriday) non activées par défaut.

Pour personnaliser l'output de conversion, ajoutez une section `[blackfriday]` au fichier `config.toml` de votre site comme suit :

```toml
[blackfriday]
  hrefTargetBlank = true
  fractions = false
```

Les remplacements du processus par défaut du thème Markdown sont disponibles à partir du front matter, ce qui vous permet de contrôler à un niveau page par page.

Regardez la documentation Hugo pour des [options de configuration](http://gohugo.io/overview/configuration/#configure-blackfriday-rendering) supplémentaires.

### Shortcodes

Gardez votre contenu <abbr title="Don't Repeat Yourself ou Ne vous répétez pas">DRY</abbr> et augmentez la cohérence thématique sur tout votre site. Pour aider à atteindre cet objectif, Hugo fournit des [Shortcodes](https://gohugo.io/extras/shortcodes).

Les shortcodes sont très puissants et peuvent être utilisés pour parvenir à des fonctionnalités qui ne pourraient être disponibles autrement dans le processeur markdown. Hugo dispose de [shortcodes intégrés](https://gohugo.io/extras/shortcodes#built-in-shortcodes) que vous pouvez utiliser sur votre site et le thème After Dark en fournit aussi d'autres.

Voici le shortcode `blockquote` fourni par After Dark :

```html
<blockquote {{ with .Get "class" }}class="{{ . }}"{{ end }} {{ with .Get "citelink" }}cite="{{ . }}"{{ end }}>
  {{ .Inner }}
  {{ with .Get "citelink" }}
    <cite><a target="_blank" href="{{ . }}">{{ $.Get "cite" }}</a></cite>
  {{ else }}
    <cite>{{ .Get "cite" }}</cite>
  {{ end }}
</blockquote>
```

Utilisez-le dans vos fichiers markdown comme suit :

```html
{{</* blockquote cite="Bitly" citelink="https://bitly.is/2mkxskj" */>}}
  <p>Quand vous créez votre propre Domaine Raccourci à Votre Marque, vous pouvez vous attendre à une augmentation de 34% de CTR comparé aux liens standards bit.ly.</p>
{{</* /blockquote */>}}
```

Voici les shortcodes supplémentaires fournis par le thème qui sont à votre disposition : 

- `figure` - Similaire à celui intégré dans Hugo, mais avec le [Chargement Paresseux Intelligent](#intelligent-lazy-loading), un titre de miniature ajusté et un texte de miniature plus petit.

Sont aussi inclus un certain nombre de shortcodes pour les [composants hackcss](https://hackcss.egoist.moe/) qui fonctionnent sur les [variantes de thème](#variantes-de-thème) After-Dark :

- `hackcss-alert` - Fournit des boîtes d'alerte thématiques. Voir `hackcss-alert.html` pour les notes d'usage.
- `hackcss-button` - Fournit des boutons thématiques. Voir `hackcss-button.html` pour les notes d'usage.
- `hackcss-buttongroup` - Permet aux boutons d'être groupés ensemble. Voir `hackcss-buttongroup.html` pour les notes d'usage.
- `hackcss-card` - Fournit un élément de carte dans le thème. Voir `hackcss-card.html` pour les notes d'usage.
- `hackcss-progress` - Fournit un compteur de progrès dans le thème. Voir `hackcss-progress.html` pour les notes d'usage.
- `hackcss-throbber` - Fournit un indicateur de chargement dans le thème. Voir `hackcss-throbber.html` pour les notes d'usage.

Pour créer vos propres shortcodes personnalisés, ajoutez un dossier `layouts/shortcodes` sur votre site, placez vos shortcodes dedeans et commencez à les utiliser dans votre contenu markdown.

La référence dans la doc Hugo pour les [instructions d'usage d'un shortcode](https://gohugo.io/extras/shortcodes#using-a-shortcode).

### Surbrillance de Syntaxe

Fournissez une expérience améliorée quand vous partagez des échantillons de code sur votre site. After Dark fournit un support en opt-in pour la surbrillance de code en utilisant les jolis thèmes [One Dark](https://github.com/atom/one-dark-syntax) et  [One Light](https://github.com/atom/one-light-syntax) de Pygments.

{{< figure
  src="/img/gohugo/feat-syntax-highlighting.jpg"
  caption="Mise en valeur de syntaxe utilisant Atom One Pygments"   
  class="lazyload" 
  >}}
  
Pour régler la surbrillance de syntaxe pour votre site After Dark :

- Suivez les instructions d'[installation Pygments](https://gohugo.io/extras/highlighting/#pygments) d'Hugo.
- Ouvrez le dossier `themes/after-dark` et lancez `npm i` (suppose que NPM soit installé).
- Puis ouvrez `./node_modules/atom-one-pygments` et `npm i`.
- Une fois les dépendances installées, lancez `npm run build` dans le module pour générer les feuilles de style vers le dossier `./dist` du module.

Puis choisissez soit `./dist/light.css` ou `dark.css` selon votre [Variante de Thème](#variantes-de-thèmes) et copiez les contenus du fichier dans votre fichier [Styles Personnalisés](#styles-personnalisés).

Une fois configuré, la surbrillance de syntaxe avec Pygments peut être activée en utilisant le [shortcode `highlight`](https://gohugo.io/extras/shortcodes#highlight) intégré dans Hugo. Référence à la doc de Surbrillance de Syntaxe pour les [instructions d'usage](https://gohugo.io/extras/highlighting/#usage).

**Pas entièrement satisfait ?** [Atom One Pygments](https://github.com/comfusion/atom-one-pygments) est construit comme un thème, rendant possible la modification du résultat de la surbrillance de syntaxe. Fabriquez la vôtre. Regardez le [README](https://github.com/comfusion/atom-one-pygments/blob/master/README.md) pour plus de détails.

### Personnalisation

After Dark utilise [hack.css](https://hackcss.egoist.moe/dark.html) pour styliser automatiquement votre markup, vous donnant accès aux grilles flexbox, aux variantes de thème clair/foncé, et d'autres composants pré-construits. Utilisez-les pour créer de nouvelles  [sections](#section-menu) tirant avantage des [modèles block](https://gohugo.io/templates/blocks). Options de personnalisation supplémentaires listées ci-dessous.

#### Styles personnalisés 

Pour ajouter vos propres styles au thème ou remplacer la CSS existante sans avoir à modifier les fichiers du thème, faites ce qui suit :

1. Créez un fichier `critical-custom.css` dans votre dossier du site `layouts/partials`.
1. Ajoutez vos styles personnalisés dans le fichier.

Exemple de personnalisation de fichier :

```css
/* override theme defaults */
.muted {
  color: rgba(255, 255, 255, 0.5);
}
/* custom styles */
figure {
  margin-left: auto;
  margin-right: auto;
  text-align: center;
}
figure img {
  max-width: 80%;
}
figure a {
  border-bottom: none !important;
}
figure a:hover {
  background-color: inherit !important;
}
```

Vos personnalisations devront être placées dans la ligne à l'intérieur de la section `head` de chaque page, remplaçant les styles existants si spécifiés.

#### Variantes de Thème

[`hack.css`](http://hackcss.com/) fournit quelques variantes que vous pourriez utiliser au lieu du thème par défaut After Dark. Pour télécharger les variantes, faites un `npm i` à partir de `/themes/after-dark/` (suppose que vous ayez installé NPM).

Une fois téléchargé, ouvrez le dossier  `node_modules/hack/dist` et remplacez les contenus de `critical-vendor.css` avec la CSS que vous souhaitez utiliser, en mettant à jour le réglage `theme_variant` dans le fichier de config du site comme suit : 

    theme_variant = "standard dark-grey"

**Pourquoi ne pas utiliser des fichiers externes CSS ?** After Dark est optimisé pour la vitesse, et limite par conséquent le nombre de requêtes HTTP à chaque fois que cela est possible. Les concessions pour les CSS externes pour le support HTTP/2 Push State seront produites sur demande.

Une fois le fichier du fournisseur mis à jour, ouvrez vos outils de développement préférés et testez les modifications en prévisualisant votre site sur le mobile, la tablette et le bureau à différentes résolutions et orientations d'affichage, en faisant  les réglages nécessaires sur `critical-theme.css`.

Et pour finir, ajustez si besoin vos [Styles Personnalisés](#styles-personnalisés), votre page 404 et `/meta/theme-color`.

#### Favicon

After Dark est livré pré-installé avec une toute petite favicon SVG embarquée dans chaque page. Pour la personnaliser, créez un fichier appelé `favicon.html` sous `/layouts/partials` dans votre site et placez un [lien `icon`](http://devdocs.io/html/link_types#icon) à l'intérieur.

**Pourquoi SVG ?** Simple. Les favicons ont une taille de fichier plus petite et sont plus flexibles. Les favicons SVG peuvent être stylées avec CSS ou même animées avec JavaScript. Firefox les supporte depuis la Version 41, et vous pouvez prévisualiser l'icône actuelle sur bien d'[autres navigateurs](http://caniuse.com/#feat=link-icon-svg).

## Licence du thème 

Le thème After-Dark est sous Copyright © 2016-2017 Josh Habdas <josh@habd.as>.
<br>Vous pouvez le redistribuer ou le modifier sous les termes de la Licence "Do What The Fuck You Want To Public License", Version 2,
<br>telle que publiée par Sam Hocevar.

## Conclusion 

Un magnifique thème à [bricoler](http://gohugo.io/themes/customizing/) et à prescrire à tous les enfants de hackers faisant leurs premiers pas dans le code.

[lazysizes]: https://github.com/aFarkas/lazysizes