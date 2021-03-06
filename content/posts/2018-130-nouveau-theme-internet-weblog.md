---
title: "Nouveau Theme Internet Weblog"
date: 2018-05-10T12:29:58+02:00
draft: true
---

Changement de thème pour cette motorisation GoHugo. Choisi le thème [internet weblog](https://themes.gohugo.io/internet-weblog/) créé par Josh Johnson. Un look de blog associant un flux de microblog (posts sans titre) et de photoblog. 

`internet-weblog` est un thème Hugo minimaliste (et un peu responsive) qui offre également la possibilité de faire des liens simples de post reliés à une page distante. Il a été porté d'un thème conçu pour Octopress.

Le thème comprend une section bio personnalisable et un flux de photos basé sur flickr dans le pied de page, une mise en page pour afficher tous les posts triés par année, et un support pour les partiels afin de personnaliser le style et le javascript.

L'installation se fait classiquement en déclarant le thème dans le fichier `config.toml`.

Il y a quelques concepts que ce thème emploie pour créer un blog personnel. Parce que ce thème est conçu pour être un blog personnel, il opte pour des simplifications comme l'utilisation de l'option du “Section Menu for the Lazy Blogger” dans Hugo pour afficher un menu simple. Cela suppose que vous appelez les articles de votre blog et les organisez comme tels. 

Par exemple,  créer un nouveau post (ou micropost, ou photopost) avec Hugo nécessiterait de taper :

```bash
  $ hugo new posts/mon-nouveau-post.md

  $ hugo new microposts/pensee-rapide.md

  $ hugo new photos/mes-vacances-en-hongrie.md
```

Cela suppose également que vous souhaitez afficher des liens vers vos sections de contenu (posts, microposts, photos) et que vous souhaitez afficher des liens vers d'autres pages du menu et cela nécessite une certaine configuration de votre part. Ce guide vous emmènera à travers les étapes pour configurer votre blog pour utiliser le thème.  

### Configurer votre Blog

#### Où devraient être stockés vos fichiers de blog en markdown 

Le thème fonctionne avec d'autres types de contenus, mais les posts fonctionnent le mieux lorsqu'ils sont regroupés dans le dossier `posts`. Si vous utilisez le type de contenus `posts` (_notez qu'il est au pluriel_) vous aurez une page de liste personnalisée classée par année et la page de liste par défaut. Voici un exemple :

![Page Liste personnalisée par Année](https://github.com/jnjosh/internet-weblog/raw/master/images/posts.png)

**Recommandation :** Organisez vos posts de blog dans le dossier `posts`.

#### Comment configurer le menu dans la navigation du blog

Comment mentionné plus haut, ce thème adopte approche simplissime pour les menus. En fait, il ne prend pas vraiment en charge les menus personnalisés optant à la place pour l'utilisation du menu `main` d'Hugo. Parce qu'il utilise la [“Section Menu for the Lazy Blogger”](https://gohugo.io/extras/menus/#section-menu-for-the-lazy-blogger), vous devrez faire une modification dans votre fichier `config.toml`. Ajoutez **main** à la `SectionPagesMenu`.
    
    SectionPagesMenu = "main"
    
Pour cette raison, vos posts individuels n'ont pas besoin d'être organisés à l'intérieur de groupes de menus. Tout est supposé être groupé au niveau le plus haut. Une exception à ceci, c'est si vous voulez ajouter une page personnalisée à la racine du menu. Dans ce cas, vous ajouterez `menu: main` au Front Matter de votre page.

Vous pouvez contrôler quels sont les éléments du menu qui reçoivent une icône RSS et faire un lien en ajoutant la liste `RSSSections` à votre section Params de votre  `config.toml` :
    
    [params]
    	RSSSections = [ "Posts", "Microposts", "Photos" ]
    

Vous pouvez ensuite contrôler le nom et le poids de ces menus dans votre `config.toml` en ajoutant une section pour chaque élément de menu que vous aimeriez afficher :
    
    [[menu.main]]
      name = "Posts"
      weight = 1
    	identifier = "posts"
      url = "/posts/"
    
Si vous n'être pas sûr de ce à quoi cela pourrait ressembler, regardez comment [jnjosh.com utilise ça dans son config.toml](https://github.com/jnjosh/jnjosh.com/blob/master/config.toml).

**Recommandation :** Ajoutez `SectionPagesMenu` à votre fichier  `config.toml`. **Recommandation :** Ne réglez pas un `menu` dans le Front Matter de votre post à moins de vouloir l'afficher sur la navigation. **Recommandation :** Personnalisez les menus qui reçoivent une icône RSS en ajoutant le paramètre `RSSSections` à votre fichier `config.toml`. **Recommandation :** Configurez les éléments du menu en ajoutant des sections `menu.main` à votre fichier  `config.toml`.

#### Vous définir vous-même comme l'Auteur

Il semble que la plupart des thèmes utilisent la variable `author` pour ajouter quelque chose comme votre nom. Ce thème utilise de la data plus structurée vous concernant et il requiert une section `[author]`. Les détails de ce qui est affecté par chaque propriété est défini en-dessous dans la section variables, mais vous devriez ajouter cette section à votre `config.toml` :
    
    [author]
    	Handle = "<Votre `handle`>"
    	FirstName = "<Votre Prénom>"
    	LastName = "<Votre Nom de Famille>"
    	AboutPage = "<Le lien relatif ou complet vers votre page à  propos>"
    	Location = "<Votre Lieu>"
    	FlickrID = "<Votre ID Flickr>"
    

**Recommandation :** N'utilisez pas la variable `author`, utilisez la section `[author]` du dessus dans votre `config.toml`.

#### Personnaliser la Section Bio, la page 404, javascript, ou les feuilles de style

Il y a quelques points d'entrées que vous devez personnaliser. Le plus important étant le partiel `bio.html`. Les contenus de ce fichier sont affichés dans la partie gauche du pied de page. Pour la personnaliser, ajoutez un fichier `bio.html` dans le répertoire de votre site sous `layouts/partials`.

Plus de détails sur chacun de ces fichiers à remplacer peuvent être trouvés sous la section [remplacements](https://themes.gohugo.io/internet-weblog/#overrides).

**Recommandation :** Ajoutez un fichier `layouts/partials/ bio.html` à votre site qui en dira plus à vos lecteur vous concernant.

#### Créer un Post Lien

Parfois, vous voulez un post qui ne contient que des liens vers un autre site Web. Cela peut être fait en incluant le paramètre `externalurl` sur votre post individuel. Un post-lien est juste un post normal sous `posts` qui a ce paramètre spécial. Par exemple, dans un article qui parle d'un projet kickstarter, vous pouvez ça au Front Matter de votre post individuel :

    externalurl = "http://kickstarter.com"
    

Ces posts sont restitué légèrement différemment avec une → pour signifier que c'est un lien externe.

![URL externe](https://github.com/jnjosh/internet-weblog/raw/master/images/linkpost.png)

### Variables

Variable Quelle valeur ? Requise

`theme`
`internet-weblog`
Seulemement si vous voulez utiliser ce thème ! 😃

`title`
`internet weblog`
Non. À moins que vous ne vouliez appeler votre blog quelque chose d'autre.

`SectionPagesMenu`
`main`
Oui. Voir [au-dessus](https://themes.gohugo.io/internet-weblog/#configuring-your-blog).

`[author]` - `Handle`
Un handle court pour vous décrire. Ceci pourrait être votre handle twitter ou simplement votre prénom. 
Oui. Ceci est utilisé pour générer le Titre du Site.

`[author]` - `FirstName`
Votre Prénom.
Oui. Ceci est utilisé dans le pied de page pour dire Bonjour et à d'autres endroits pour vous identifier comme l'auteur.

`[author]` - `LastName`
Votre nom de famille
Pas vraiment. Il est utilisé à quelques endroits pour vous identifier comme l'auteur.

`[author]` - `AboutPage`
`/about` ou `http://about.autre.com`
Seulement si vous voulez une page à propos. Ceci est exposé pour vous permettre de faire aussi un lien vers une page externe à-propos. Si vous avez une page locale, ce peut être juste quelque chose de relatif.

`[author]` - `Location`
`Your City`
Non. Si c'est réglé, ceci est ajouté au Copyright dans le pied de page afin que vous puissiez donner un peu d'amour à votre ville de résidence.

`[author]` - `FlickrID`
`Your Flickr ID`
Non. Le pied de page affiche votre flux de photo extrait de  flickr. Si vous ne voulez pas l'installer, rien ne sera affiché.

`[params]` - `Description`
`Describe your site`
Non. Si c'est réglé, ceci est ajouté aux métadonnées de vos pages.

`[params]` - `ShowCopyright`
`true` ou `false`
Non. Si true, le texte Copyright sera ajouté au pied de page.

`[params]` - `RSSEnabled`
`true` ou `false`
Non. Si true, les pages RSS seront générées.

`[params]` - `RSSSections`
`[ "Posts", "Microposts", "Photos" ]`
If you want RSS links in the menu, yes. These strings need to be the display name of the section where you want to have an RSS icon displayed. ![rss](https://raw.githubusercontent.com/jnjosh/internet-weblog/master/images/rss.png)

`[params]` - `RSSMicropostTitles`
`true` or `false`
No. If false, Microposts RSS feeds will not have the title in included posts. If not present or true, nothing happens.

`[params]` - `YearlyMicroposts`
`true` or `false`
No. If true, Microposts will have a page with a yearly grouping just like the posts. If not present or false, nothing happens.

Voici un exemple de fichier  `config.toml` :
    
    baseurl = "http://mysite.com/"
    languageCode = "en-us"
    title = "internet weblog"
    theme = "internet-weblog"
    Paginate = 10
    SectionPagesMenu = "main"
    
    [author]
    	Handle = "jnjosh"
    	FirstName = "Josh"
    	LastName = "Johnson"
    	AboutPage = "/about"
    	Location = "Durham, NC"
    	FlickrID = "87151163@N00"
    
    [params]
    	Description = "This is my blog, read it and enjoy."
    	ShowCopyright = true
    	RSSEnabled = true
    	RSSSections = [ "Posts", "Microposts", "Photos" ]
    
    [taxonomies]
    	tag = "tags"
    	category = "categories"
    	series = "series"
    
    [[menu.main]]
      name = "Posts"
      weight = 1
    	identifier = "posts"
      url = "/posts/"
    
    [[menu.main]]
    	name = "Microposts"
    	weight = 2
    	identifier = "microposts"
    	url = "/microposts/"
    
    [[menu.main]]
    	name = "Photos"
    	weight = 3
    	identifier = "photos"
    	url = "/photos/"
    

### Remplacements 

Le thème vous demande de remplacer quelques fichiers dans votre blog pour finaliser la personnalisation de votre blog. Voici une liste des fichiers que vous pouvez remplacer et pourquoi. Pour les remplacer, créez votre propre version du fichier sous `layouts/partials` -vous devrez peut-être créer ce répertoire.

Fichier Pouquoi le remplacer? Requis

`bio.html`
Le pied de page du blog met en avant une section vous concernant. 
Oui. Autrement, ce sera simplement le texte par défaut.

`not_found.html`
Si vous voulez personnaliser la page 404 not found, vous pouvez la mettre à jour ici.
Probablement. Celle par défaut est vraiment brute.

`custom_javascript.html`
Si vous avez besoin que toutes les pages aient vos propres fichiers javascript référencés, vous pouvez le faire ici.
Non

`custom_stylesheets.html`
Si vous avez besoin que toutes les pages aient vos propres feuilles de style personnalisées, vous pouvez le faire ici. 
Non

`custom_image_handler.html`
Le pied de page du blog fait apparaitre un flux de photo. Si vous souhaitez le personnaliser ou utiliser une source différence, vous pouvez remplacer ce comportemement.
Non

## Contribuer

Vous avez trouvé un bug ou vous avez des idées de nouvelles fonctionnalités ? Sentez-vous libre d'utiliser le "issue tracker " pour me le faire savoir ou faites une pull request.

## Librairies Tiers

Ce thème fait usage de Librairies Tiers 

  * [lightGallery v1.2.14](http://sachinchoolur.github.io/lightGallery/) - Utilisé dans le pied de page pour fournir une galerie pour visualiser les photos dans le flux photo.

## Licence

Ce thème est sous licence MIT. Pour plus d'informations, regardez SVP la [Licence](http://jnjosh.mit-license.org/).

## Contact

Ceci est le premier thème que j'ai produit pour Hugo, aussi soyez certains que j'ai du faire quelques erreurs. Si vous avez des idées ou choses qui devraient être réparées, SVP faites-le moi savoir.

  * [Josh Johnson](http://jnjosh.com/) [@jnjosh](http://twitter.com/jnjosh)


  

