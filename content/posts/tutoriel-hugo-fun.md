---
title: "La Création Web Plus Fun avec Hugo"
date: 2017-07-20T16:21:07+02:00
draft: true
---

Comment créer votre site de dév avec Hugo

<!--more-->

[Source](https://code.tutsplus.com/tutorials/make-creating-websites-fun-again-with-hugo-the-static-website-generator-written-in-go--cms-27319 "Permalien vers Make Creating Websites Fun Again With Hugo")

Les sites statiques sont populaires pour de nombreuses raisons. En évitant les solutions surdimensionnées et en gardant un projet simple sans bases de données, sans trop de dépendances ou de configurations spécifiques du serveur (pas de PHP, ni MySQL / MSSQL, .NET, Python, Ruby, etc.), cela les rend très simples à déployer et ils sont robustes contre de nombreuses vulnérabilités possibles. En fin de compte, ceux-ci deviennent de simples pages HTML de base servies à l'utilisateur.

Dans ce guide, je vais vous montrer comment configurer votre environnement de développement avec Hugo et créer votre premier site statique [Hugo][1].

## Une toute nouvelle approche sur les sites Web statiques

L'acronyme légendaire de design KISS - _Keep It Simple, Stupid_ - peut être appliqué à Hugo et à sa façon d'approcher l'espace des générateurs de sites statiques.

Construit en Go, Hugo compile rapidement vos pages statiques (il faut quelques fractions de millisecondes pour compiler un petit site - et il peut produire des milliers de pages en quelques secondes).

Hugo fournit également des outils essentiels au workflow du site statique (y compris les outils de déploiement et de migration), permettant aux développeurs et aux concepteurs de se concentrer sur les parties amusantes, telles que l'exercice de leur créativité et la mise en œuvre de cette créativité dans la construction du site.

### Pourquoi des Sites Web Statiques ?

Lorsque nous construisons des sites web basés sur le contenu, nous pouvons prendre certaines généralités sur tous les sites et Hugo donne un cadre pour cela. Plus précisément, nous pouvons prendre des types de contenu tels que des publications, des catégories, des revues ou des produits et organiser les données. Ensuite, nous pouvons donner à chacun un regard spécifique via des modèles et des feuilles de style.

À l'avenir, nous pouvons alors conduire tout ce dont nous avons besoin dans l'espace statique HTML/CS/JS statique. Lorsque vous pensez à cela de façon pragmatique, c'est un grand espace qui laisse de la place à beaucoup de créativité.

JQuery fonctionnera bien et rien ne vous empêchera d'utiliser si vous en avez besoin des services tiers sur votre page statique. Ne vous limitez donc pas en pensant que vous ne pouvez pas intégrer d'autres bibliothèques ou applications dans vos sites statiques. Ce n'est vraiment pas le cas. Vous pouvez utiliser n'importe laquelle des bibliothèques JavaScript disponibles.

Aussi valable pour un site Web de type brochure d'entreprise avec quelques pages avec un lien vers une page Google Forms pour nous contacter. Et si vous devez afficher d'autres types de données, vous pouvez utiliser JavaScript pour cet aspect de votre site.

### Comment ça Marche pour Mon Business et Mes Clients ?

Prenez, par exemple, un petit magasin ou un freelance avec quelques produits ou services qui ne nécessitent pas une solution eCommerce complète. Au lieu de cela, il n’a besoin que des informations sur le produit et un lien "contact" sur la page. Hugo peut faire ça en une matinée. L'hébergement même n’est pas un souci - c'est une réflexion après-coup, vraiment, car nous servons simplement des pages HTML de base.

Hugo fonctionne également bien pour de la documentation de projet sur les projets GNU. Pensez par exemple, à des start-up ou des PME qui ont besoin d'une présence simple.

### Quelles sont les Limites des Sites Statiques ?

Ce qu’Hugo ne sait pas faire, c'est le contenu **dynamique**, par exemple, les formulaires basés sur la base de données, la recherche ou les systèmes utilisateurs. Si c'est ce que vous cherchez, Hugo n’est sûrement **pas** ce que vous voulez. Mais pour les autres cas, quand vous vous dites "pourquoi ne pas simplement mettre en place une page de base pour cela ? », les générateurs de sites Web statiques sont une option solide. Sachez aussi que Hugo n'est pas le seul générateur de site statique. Il en existe beaucoup d’autres qui fonctionnent depuis longtemps, [vous trouverez ici][2] une liste de ceux-ci.

Pour créer des blogs de contenu en direct comme des sites d'information, Hugo pourrait être une excellente solution pour monter rapidement une page afin que cette couverture soit liée à partir de votre site principal, la mettre en ligne en quelques minutes, ce qui signifie que vous pouvez continuer à y ajouter rapidement et redéployer les modifications très rapidement. Mais pour faire un site de nouvelles complet avec la recherche et de nombreux écrivains, il n’est vraiment pas approprié d'utiliser Hugo.

Hugo pêche aussi dans l’utilisation des outils plus avancés pour son pipeline d'actifs tels que ES6 et Sass - si vous souhaitez utiliser cette technologie, vous devrez inclure Gulp ou Grunt pour faire le travail ; Sinon, vanilla CSS et JavaScript fonctionnent mieux.

## Votre Environnement de Développement Maison 

Hugo est écrit en Go et il est supporté par de nombreuses plates-formes. Pour afficher toutes les versions, vous pouvez [aller ici][3].

Pour les utilisateurs de MacOS avec HomeBrew, l'installation peut se faire comme suit :

`brew update && brew install hugo`

Plus d'informations sur l'installation de [Mac OSX][4] et [Windows][5]

Une fois Hugo installé, nous pouvons tester l'installation en exécutant `hugo help` dans l'invite de commande ou `hugo version`.

## Faire votre premier site Web statique avec Hugo

Maintenant que nous avons installé Hugo, nous pouvons commencer à créer le site. Lancez la commande suivante en remplaçant ‘votre-nom-de-site-ici' par votre nom de projet :

```bash
    $ Hugo new site votre-nom-de-site-ici
```
Ceci créera une première structure pour votre site, que vous pourrez visualiser dans votre finder.

![Fichiers par défaut Hugo][6]

Ou dans votre terminal via la commande `tree`

![Voir les fichiers hugo avec la commande tree dans le terminal][7]

Hugo a créé 6 sous-répertoires et 1 fichier, qu'il utilise pour créer le site web final. À partir d'ici, voici ce qu'ils veulent tous dire :

* **archetypes** : nous définissons ici ce qu'est notre contenu, nous pouvons définir des tags ou des catégories par défaut et définir ici des types tels qu'un post, un tutoriel ou un produit
* **config.toml** : la configuration principale est ici, nous pouvons définir tous les titres du site, langue, URL, etc.
* **content** : les pages de contenu du site sont stockées ici, les sous-répertoires sont utilisés pour les [sections][8] afin d'aider à organiser le contenu, créer un «content/produits» pour le contenu de vos produits par exemple
* **data** : les données du site, telles que les configurations de localisation vont ici
* **layouts** : les [layouts][9] (mise en page) pour la bibliothèque Go html/template utilisée par Hugo vont ici.
* **static** : tous les [fichiers statiques][10] posés ici seront compilés dans le site Web final. La liberté totale est autorisée afin que vous puissiez servir par exemple n'importe quel fichier css, js ou image.
* **themes** : Créez de nouveaux thèmes ou clonez des thèmes de github dans ce répertoire pour les utiliser avec votre site.

## "Hello World" dans Hugo  

Nous devons ajouter un post pour voir le site que nous venons de créer, faites ça en utilisant la commande suivante : 
 
```bash       
    $ hugo new post/premier-post.md
```

Maintenant éditez le fichier dans `content/post/premier-post.md`, il contiendra quelque chose de similaire à ce qui suit par défaut : 

```yaml
    ---
    date: "2017-06-26T13:19:03+07:00"
    title:"premier post"
    draft: false
    ---
```
### Front Matter

Le contenu à l’intérieur de `---` est la configuration YAML pour le post. Cette configuration s’appelle **front matter**. Elle vous permet de définir la configuration du post avec son contenu. Par défaut, chaque post aura les propriétés de configuration présentées au-dessus.

Ajoutez un peu de texte après le `---` comme suit :

```yaml
    ---
    date: "2017-06-26T13:19:03+07:00"
    title: "premier post"
    draft: false
    
    ---
    
    Hello world!
```   

### Servir les Données et Rechargement Live

Nous pouvons voir ici la fonctionnalité de live reload qui est intégrée nativement dans Hugo. Effectuons quelques modifications sur le site et regardons ce qui s'y passe.

Tout d’abord, démarrez le serveur en lançant : 

```bash    
    $ hugo server
```    

Maintenant, si vous faites quelques modifications à votre fichier, vous verrez Hugo se rafraîchir instantanément.

Votre site web sera disponible sur <http://localhost:1313> mais  _**attention**_ - vous ne verrez qu'une **page blanche vide** à ce stade, parce que nous n'avons pas défini de thème !

## Ajouter un Thème

Hugo dispose d'une bibliothèque de thèmes très robuste et versatile car il utilise la bibliothèque `html/template` de Go. Les thèmes sont faciles à travailler, l'installation se fait en clonant simplement le repository d'un thème dans le dossier `themes` de votre site Hugo. 

Hugo n'arrive pas avec un thème par défaut. aussi vous **devez** en installer un.

Il existe plein de thèmes open source [à choisir ici][11].

Ajoutons des paquets de thèmes à notre site, ainsi nous pouvons jouer avec eux et voir ceux que nous apprécions. Faites ça en lançant ce qui suit dans notre répertoire Hugo : 

```bash    
    $ git clone --recursive https://github.com/spf13/hugoThemes.git themes
    
    Cloning into 'themes'...
    remote: Counting objects: 880, done.
    remote: Compressing objects: 100% (5/5), done.
    remote: Total 880 (delta 1), reused 0 (delta 0), pack-reused 875
    Receiving objects: 100% (880/880), 669.20 KiB | 288.00 KiB/s, done.
    Resolving deltas: 100% (506/506), done.
    Checking connectivity... done.
```    
    
Vous verrez maintenant un tas de thèmes clonés dans votre site. Il y en a beaucoup, alors vous aurez le temps de faire une pause pendant qu'il clone ...

![Un paquet de thèmes sont disponibles pour Hugo][12]

### Utiliser un Thème

Pour utiliser un thème, lancez simplement Hugo avec le paramètre  `-t` ou `\--theme` comme suit
 
```bash    
    $ hugo -t NomTheme
```

Ou vous pouvez ajouter à votre fichier `config.toml` :

```toml        
    theme: "NomTheme"
```

Le _NomTheme_ doit correspondre au nom du répertoire à l'intérieur de `/themes`.

Lorsque vous avez choisi un nom de thème dans le répertoire, démarrez votre serveur avec `hugo server --theme=NomTheme` et regardez <http://localhost:1313>

Voici quelques exemples de certains de ces thèmes que nous avons clonés, j'ai utilisé `beg`,` crisp` et `cactus`, jetez un oeil il y en a tant à choisir !

![Le thème beg sur votre écran de téléphone mobile fonctionnera merveilleusement bien][13] ![Un exemple du thème crisp extrait du repo theme d'Hugo][14] ![Un exemple de test de thème dans Hugo avec votre premier post][15]

Ainsi, vous avez désormais généré un site web avec un post hello world, que pouvons-nous faire d'autre ?  

## Construire un Blog

Produire un blog basique est vraiment facile à faire avec Hugo. Tout d'abord, vous devez définir un archetype pour le post par défaut, aussi créez un nouveau fichier dans 'archetypes/default.md` et ajouter ce qui suit comme **front matter** :
    
```toml    
    +++
    tags = ["welding", "metal work"]
    categories = ["posts"]
    +++
```

Nous réglons ici des balises par défaut, pour un blog sur la soudure, nous pouvons être sûrs que nous voulons que ces tags soient présents sur tous nos messages, et nous créons une catégorie appelée posts juste pour que nous ayons une valeur par défaut lorsque nous créons un post.

Ajoutez maintenant votre premier post via le terminal de la manière suivante :

```bash
    $ hugo new post/tig-welding-a-bike-frame.md
```
Ceci créera un post avec l'archétype défini au-dessus, vous pouvez désormais l'ouvrir dans un éditeur de texte et commencer à écrire en format markdown !

Ajoutons quelques posts supplémentaires : 

```
    $ hugo new post/welding-a-roll-cage.md
```

A nouveau pour ajouter du contenu, ouvrez simplement le fichier Hugo créé et commencez à ajouter du contenu à la fin du fichier après le front matter.

## Construire une Galerie de Photos 

Pour construire une galerie de photos avec Hugo, nous utiliserons l'excellent outil `hugo-gallery` disponible sur [GitHub][16]. 

Son usage se fait comme suit : 

```bash
    $ hugo-gallery <Chemin Source> <Section Destination> <Titre> [UrlBase]
```
L'outil `hugo-gallery` créera un nouveau répertoire posts contenant un fichier markdown pour chaque image dans le répertoire source permettant un diaporama ordonné. Il lira tous les fichiers tirés du répertoire `Chemin Source`  et les sauvegardera dans le répertoire statique du site Hugo.

Il créera un nouveau répertoire à l'intérieur du répertoire content basé sur le `Titre` fourni par ex. `content/welding`

Par exemple :
```bash    
    $ hugo-gallery static/images/welding-photos welding "Photos of my insane welding skills"
```

Visitez `localhost:1313/welding` pour voir le contenu.

## Déploiement

Hugo dispose de plusieurs outils de déploiement tels que [hugomac][17] qui est une application de menus OSX permettant à l'utilisateur de publier facilement sur l'hébergement EC2. Aucune ligne de commande n'est nécessaire.

De même [hugodeploy][18] fournit une configuration SFTP à déployer, ou vous pouvez simplement utiliser les [Déploiements automatisés][19] livrés avec Hugo.

## Conclusion

Les générateurs de sites statiques existent depuis un certain temps, et Hugo construit vraiment sur un ensemble d'outils, il est rapide et facile de produire des sites, ou même de migrer un site existant de [WordPress][20] vers Hugo. Il existe beaucoup d'outils pour Hugo, y compris des éditeurs front-end, [regardez-les][21].

À l'avenir, ce serait bien de voir plus de modules pour que Hugo puisse supporter par exemple des choses comme un formulaire de contact et une galerie, ou les posts en rapport.

La [feuille de route d'Hugo][22] a beaucoup d'idées qui sortent comme le redimensionnement dynamique de l'image, le support de rsync et l'importation d'images à partir des fournisseurs d'hébergement et un hébergement plus facile avec l'intégration AWS EC2 et GitHub.

Si vous n'utilisez pas encore Hugo, n'oubliez pas de vérifier le projet à mesure qu'il se développe !

[1]: https://gohugo.io/
[2]: https://www.staticgen.com/
[3]: https://github.com/spf13/hugo/releases
[4]: https://gohugo.io/tutorials/installing-on-mac/
[5]: https://gohugo.io/tutorials/installing-on-windows/
[6]: https://cms-assets.tutsplus.com/uploads/users/1160/posts/27319/image/hugoscreen1.jpg
[7]: https://cms-assets.tutsplus.com/uploads/users/1160/posts/27319/image/hugoscreen2.jpg
[8]: https://gohugo.io/content/sections/
[9]: https://gohugo.io/templates/overview/
[10]: https://gohugo.io/themes/creation#static
[11]: https://themes.gohugo.io/
[12]: https://cms-assets.tutsplus.com/uploads/users/1160/posts/27319/image/hugo3.jpg
[13]: https://cms-assets.tutsplus.com/uploads/users/1160/posts/27319/image/hugo6.jpg
[14]: https://cms-assets.tutsplus.com/uploads/users/1160/posts/27319/image/hugo5.jpg
[15]: https://cms-assets.tutsplus.com/uploads/users/1160/posts/27319/image/hugoscreen4.jpg
[16]: https://github.com/icecreammatt/hugo-gallery
[17]: https://github.com/nickoneill/hugomac
[18]: https://github.com/mindok/hugodeploy
[19]: https://gohugo.io/tutorials/automated-deployments/
[20]: https://github.com/SchumacherFM/wordpress-to-hugo-exporter
[21]: https://gohugo.io/tools/
[22]: http://gohugo.io/meta/roadmap/

