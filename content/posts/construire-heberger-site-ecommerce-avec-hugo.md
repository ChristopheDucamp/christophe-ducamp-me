---
title: "Construire et Héberger un Site de Ecommerce Avec Hugo"
date: 2017-07-20T18:41:00+02:00
draft: true
description: Un guide pour construire votre premier site statique avec Hugo, intégrer une plateforme de e-commerce Star Trek et déployer votre site sur un Content Development Network 
---

# Tutoriel Site Web Statique Hugo avec un Exemple E-Commerce

> À la bourre ? Passez directement aux [étapes du tutoriel][1] ou au [repo GitHub + live demo][2].

Il est temps de plonger dans le monde en pleine évolution de la [JAMstack][3] et du développement web statique ! Nos publications précédentes sur le traitement du commerce électronique avec des générateurs de sites statiques tels que [Middleman][4] et [Jekyll][5] ont été assez réussies, alors pourquoi s'arrêter là, hein ?

Mesdames et messieurs, aujourd'hui, nous allons prouver combien il est facile, une fois de plus, de configurer le commerce électronique sur des sites statiques. Et cette fois-ci, nous utiliserons un didacticiel en profondeur [Hugo][6] pour le faire. :)

Le guide suivant vous présentera : 

1. Comment construire votre site statique en utilisant le générateur de sites Hugo ;
2. Comment intégrer facilement la plate-forme de e-commerce Snipcart au-dessus ;
3. Comment déployer votre site Hugo e-commerce sur Netlify.

Mais tout d'abord, un mot sur l'outil pivot que nous allons utiliser tout au long de ce tutoriel.

## Hugo : un générateur de site statique Rapide en Golang

![logo hugo générateur de site statique][7]

**Hugo** peut signifier un paquet de choses différentes pour différentes personnes. Les rats de bibliothèques pourraient penser à l'auteur légendaire des  Misérables. Les cinéphiles au petit garçon du film 2011 de Scorsese. Mais si vous êtes un **développeur** (et si vous lisez ceci, vous en êtes probablement), voici ce que vous devriez penser : _un moteur de site web statique **brûlant**, rapide et moderne_.

Écrit en [Go][8] par Steve Francia aka [** spf13 **][9], Hugo se présente comme l'une des façons les plus efficaces que nous ayons vues pour construire, gérer et mettre à jour des sites statiques modernes. Il est facile à installer sur n'importe quelle plate-forme, et en plus vous pouvez l'héberger n'importe où. Ici nous vous proposons [Netlify][10], comme vous le verrez plus loin. Et ses temps de construction sont juste hors-normes (~ 1 ms par page). Si vous aimez les performances Web autant que nous, nous pensons que vous allez aimer ce générateur de site Golang.

Aujourd'hui, je vais vous montrer comment utiliser Snipcart et Hugo pour construire un magasin de vieilleries Star Trek sur un site statique. Pourquoi Star Trek, me direz-vous ? Parce que nous [avons déjà fait Star Wars][11].

> _Psst_: toujours en train de vous demander quels sont les générateurs de site statique et pourquoi c'est important ? Jetez un oeil à cette [intro][12] d'Eduardo Bouças.

## Tutoriel Hugo : site, produits, templates & deploiement

###  1. Installer Hugo & construire votre nouveau site web statique

Tout d'abord, vous devez installer le générateur sur votre ordinateur et créer un nouveau site web. Cela vous prendra peut-être 10 minutes, en suivant la  [documentation Hugo Quickstart][13]. Ou, si vous êtes aussi rapide que Dan Hersam, **2 minutes** :

Une fois que vous aurez téléchargé la bonne version sur le [repo GitHub de Hugo][14], l'installation est une brise (comme expliqué dans la doc ci-dessus). Concentrons-nous sur la création du nouveau site Hugo.

Nous utiliserons la commande de terminal appropriée CLI pour faire juste ça :
```bash    
    hugo new site snipcart-hugo
```

**Architecture**

Cette commande générera un squelette de base pour votre projet. Vous devriez obtenir un répertoire de site qui ressemble à ça :

```bash        
    │   config.toml
    │   
    ├───archetypes
    ├───content
    ├───data
    ├───layouts
    ├───static
    └───themes
```    

Le fichier `config.toml` contiendra les réglages du site. Pour notre démo, nous n'aurons pas besoin d'epxlorer cela trop à fond, car nous ferons quelques chose de vraiment simple avec le site lui-même.

Il n'est pas nécessaire à ce stade de plonger trop  dans [le fonctionnement interne de Hugo][15]. Fondamentalement, durant ce tutoriel, nous créerons des fichiers dans le dossier `data`, qui est utilisé pour stocker des données supplémentaires qui pourraient être utilisées pour générer le site.

Nous allons également ajouter des modèles dans le dossier `layouts`, qui est l'emplacement par défaut pour stocker les modèles Hugo.

Le dossier `static` peut être utilisé pour stocker tous les éléments statiques tels que CSS, fichiers JavaScript ou images. Dans notre démo, nous ajouterons un dossier `images` contenant les images de nos produits.

Bien sûr, nous vous conseillons de vous familiariser avec la documentation Hugo avant de chercher une intégration complète de Snipcart.

**Thèmes**

Nous avons également décidé de ne pas installer de thème spécifique pour cette démo (nous utiliserons un framework CSS pour façonner notre site plus tard), mais il existe de nombreux thèmes open source disponibles. [Ce post][16] traite de la configuration des thèmes sur votre site Web Hugo, vous voudrez peut-être lui accorder une lecture. Il explore également la création basique de sites avec Hugo avec plus de détails (Hello World, blog, galerie photo, etc.).

Vous pouvez également consulter le référentiel officiel pour certains des meilleurs thèmes Hugo [ici][17].

### 2\. Création d'un fichier JSON statique pour les produits de notre magasin

Bien ! Maintenant, mettons en place nos produits: un dictionnaire Klingon et un phaser. Nous aurions pu utiliser un CMS headless ou statique pour cette partie (nous [l'avons fait][18] [avant][19]). Mais pour le but humble de cette publication, nous allons créer un fichier `.json` statique pour contenir nos produits.

Hugo fournit une fonction très soignée appelée `getJSON`. Elle peut être très utile lorsque certaines de vos données proviennent d'un CMS Headless ou de toute API qui renvoie du JSON.

Comme notre fichier JSON est directement dans le dossier de données, nous aurions pu utiliser `.Site.Data.Products` au lieu d'appeler la méthode getJSON, mais ici, nous voulions montrer qu'il est également possible d'interagir avec une API distante.

Nous devrons placer un nouveau fichier nommé `products.json` dans le dossier `data`.
    
```json   
    [{
        "id": "1",
        "name": "Klingon dictionary",
        "price": 34.87,
        "image": "/images/dictionary.jpg",
        "description": "nIvbogh tlhIngan dictionary qaStaHvIS veng SuvwI'",
        "url": "http://snipcart-hugo.netlify.com"
    }, {
        "id": "2",
        "name": "Captain Kirk Phaser",
        "description": "The Original Series Phaser comprises a small, hand-held Type I Phaser, which slots into a larger Type II Phaser body with a removable pistol-grip.",
        "price": 145.98,
        "image": "/images/phaser.png",
        "url": "http://snipcart-hugo.netlify.com"
    }] 
```

### 3\. Générer vos Templates Hugo

La prochaine étape consiste à configurer les différentes mises en page de notre site. Le plus important est le modèle d'en-tête, où nous ajouterons [les dépendances Snipcart][20].

Nous allons également créer un modèle principal dans lequel nous allons faire une boucle dans nos produits pour afficher un résumé et ajouter un «bouton d'achat» Snipcart.

_Note: Les produits Snipcart sont définis directement dans le balisage HTML avec des attributs de données simples. [Détails ici][21]._

Dans le dossier `layouts`, nous poserons un nouveau modèle **index.html**. Ce fichier sera utilisé par défaut et sera le premier généré par Hugo.

##### layouts/index.html

```html    
    {{ partial "header.html" . }}
    
    {{ $products := getJSON "/data/products.json" }}
    
    <section class="container">
        <div class="row">
            {{ range $products }}
                {{ partial "product.html" . }}
            {{ end }}
        </div>
    </section>
    
    {{ partial "footer.html" }}
```   

Au début du post, nous avons écrit à propos de la méthode `getJSON`. Nous allons l'utiliser dans notre modèle `index.html`.

Nous récupérerons les produits à partir du fichier JSON défini précédemment. Ensuite, nous suivons le produit et rendons le modèle partiel `product.html`.

Comme vous pouvez le voir, nous importons également un fichier **header.html**, **footer.html** et **product.html**. Examinons ces détails avec attention. 

Avant d'aller plus loin, nous nous dirigeons de nouveau vers le dossier `layouts` et créons des "partials". Si les fichiers partiels ne sont pas mis dans ce dossier, Hugo ne pourra pas les reconnaître comme des modèles partiels et la syntaxe {{partial ...}} ne fonctionnera pas du tout. L'autre chose importante à savoir sur ce fichier est le point "." placé après `product.html`. Cela signifie que vous incluez les données actuelles du produit dans le modèle `product.html`.

##### layouts/partials/header.html

Comme mentionné ci-dessus, ce fichier est le plus important. C'est un simple fichier d'en-tête HTML avec des dépendances Snipcart. Placez-le dans le dossier `partials` : 
    
```html
    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en-us">
    <head>
      <meta http-equiv="content-type" content="text/html; charset=utf-8">  
      <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
    
      <title> Intégration Snipcart dans Hugo ! </title>
      
      <link id="snipcart-theme" type="text/css" href="https://cdn.snipcart.com/themes/2.0/base/snipcart.min.css" rel="stylesheet">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.98.0/css/materialize.min.css">
      <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
    </head>
    
    <body>
      <div class="container">
        <nav>
          <div class="nav-wrapper">
            <a href="https://snipcart.com#" class="brand-logo">Magasin Star Trek</a>
            <ul id="nav-mobile" class="right hide-on-med-and-down">
              <li class="snipcart-summary">
                <a href="https://snipcart.com#" class="snipcart-checkout">
                  Voir le panier (<span class="snipcart-total-items">0</span>)
                </a>
              </li>
            </ul>
          </div>
        </nav>
      </div>
``` 
    
Nous avons décidé d'utiliser le framework  [MaterializeCSS][22] pour modéliser cette démo statique de commerce électronique, mais vous pouvez utiliser tout autre framework CSS. J'ai trouvé cela facile à intégrer, et il fournit suffisamment de composants intégrés pour mettre en place quelque chose qui semble propre !

Vous remarquerez également que les fichiers requis de Snipcart sont inclus dans ce modèle et que nous avons ajouté un [résumé de panier][23] pour donner aux clients un raccourci vers leur commande en cours.
 
Alors ! Etape suivante : assemblage du modèle partiel du pied de page, pour compléter le noyau de notre fichier HTML.


##### layouts/partials/footer.html
    
```html  
            <div class="container">
                <footer class="page-footer">
                    <div class="footer-copyright">
                        <div class="container">
                            Snipcart integration with Hugo
                        </div>
                    </div>
                </footer>
            </div>
            
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js" type="text/javascript"></script>
    
            <script type="text/javascript" id="snipcart" src="https://cdn.snipcart.com/scripts/2.0/snipcart.js" data-api-key="M2E5YjA3NjMtYzRiYS00YzVjLWEyYWYtNDY5ZDI0OWZhYjg5"></script>
    
            <script>
                Snipcart.execute('registerLocale', 'en', {
                    powered_by:
                    "HoS 'ej pong ngaQ "
                }); 
            </script>
        </body>
    </html>
```    

Pour finir, nous devons générer le modèle affichant les détails de nos produits Star Trek. Nommons le fichier **product.html**.

##### layouts/partials/product.html

```html   
    <div class="col s6">
    <h2 class="header">{{ .name }}</h2>
    <div class="card horizontal">
        <div class="card-image">
        <img src="{{ .image }}">
        </div>
        <div class="card-stacked">
        <div class="card-content">
            <p>{{ .description }}</p>
        </div>
        <div class="card-action">
            <button
                class="snipcart-add-item waves-effect waves-light btn"
                data-item-id="{{ .id }}"
                data-item-name="{{ .name }}"
                data-item-price="{{ .price }}"
                data-item-url="{{ .url }}">
                    <i class="material-icons right">shopping_cart</i>
                    Ajouter au panier
            </button>
        </div>
        </div>
    </div>
</div>
```    

Comme nous avons passé le produit actuel dans notre modèle **index.html**, nous pouvons maintenant utiliser tous les champs de données dans notre fichier **JSON**. Ici, je les ai utilisés pour remplir mon bouton d'achat Snipcart et ajouter le titre du produit + la description.

Il est temps de lancer notre serveur Hugo et de tester ce site chic !

```bash    
     hugo server
```      

(Je sauvegarde la capture d'écran de mon Star Trek pour la fin, faites-la vous-même !)


### 4. Régler le déploiement de Hugo sur Netlify

Enfin et surtout : accueillir tout cela !

Nous avons décidé de déployer notre démo Hugo en utilisant le service incroyable de nos amis de [Netlify][24].

Avant de tout faire dans Netlify, je suggère de créer un fichier `.gitkeep` dans votre dossier `content`. Ce dossier est requis par le robot de construction de Netlify. Et comme nous n'avons déposé aucun fichier dans ce dossier, Git va le rejeter.

Une fois le fichier `.gitkeep` en place, vous pouvez utiliser l'interface  de Netlify pour déployer facilement votre site Web en quelques secondes. Voici un aperçu de notre configuration de déploiement Brocante Star Trek :

![Paramètres de déploiement du site web hugo sur Netlify][25]

Netlify tirera automatiquement votre code sur GitHub et déploiera votre site. Et c'est tout.

![hugo-tutoriel-klingon][26]

## Live Hugo website example + GitHub repo


Aussi les mais, est-il  temps de révéler notre chef-d'œuvre Star Trek :

![Tutoriel-site-web-statique-ecommerce-hugo][27]

Est-ce que votre esprit est soufflé ou quoi ? Maintenant, vérifiez à la fois le site et le code :

> Voir la [démo live de Snipcart + Hugo][28]

> Voir mon [Repo de code GitHub][29]


## Conclusion et autres ressources

Hé les mais, je pense que notre travail ici est terminé !

Dans le cas où vous vous demandez si le résultat final est assez rapide, vous pouvez utiliser un autre outil bien cool chez Netlify : [Testmysite.io][30]. J'ai recçu une note de 100/100 avec la démo ; pas trop mal pour un début.

Bien sûr, si vous créez un site JAMstack sérieux ou pour un client, vous voudrez peut-être envisager de suivre ses performances avec [cet outil open source gratuit][31]. En outre, les équipes affutées tech pourraient vouloir examiner [ce workflow de publication pour Hugo][32].

**Clients**


Pensez-vous que le traitement des fichiers de contenu statique pilotés par Markdown ne fonctionnera pas pour les clients ? Certains outils intéressants peuvent aider à modifier et à gérer le contenu de Hugo. Nous suggérons de lancer l'un des CMS statiques suivants dans le mix :

> Pour plus d'informations sur les outils JAMstack pour les clients, les limites et les avantages, [consultez ce guide complet][33].

Jouer avec Hugo a été une joie. Sa documentation était remarquable, et sa vitesse presque instantanée faisait sourire l'ingénieur en moi, souriant à chaque fois que je reconstruisais mon site. L'élaboration de ce didacticiel Snipcart + Hugo m'a demandé environ deux heures. Et cela inclut le style du site avec MaterializeCSS et l'hébergement sur Netlify.

Cela me fait toujours plaisir de voir à quel point les générateurs de sites modernes sont bien adaptés à notre panier d'achat HTML/JS. :)

Maintenant, arrête de lire ce blog et va construire quelque chose d'extraordinaire.

[Source](https://snipcart.com/blog/hugo-tutorial-static-site-ecommerce "Permalink to Hugo Website Tutorial with a Live Static E-Commerce Example")

* * *
_Vous avez des questions concernant ce tutoriel Snipcart + Hugo ? Y-a-t-il d'autres générateurs de site statique que vous souhaitez que nous couvrions sur le blog ? Ajoutez des commentaires pour des questions, des suggestions ou pour parler Klingon. Et si vous avez apprécié cette publication, prenez une seconde pour [la partager sur Twitter][34] !_

[1]: https://snipcart.com#tutorial
[2]: https://snipcart.com#demo-repo
[3]: https://jamstack.org/
[4]: https://snipcart.com/blog/static-site-e-commerce-integrating-snipcart-with-middleman
[5]: https://snipcart.com/blog/static-site-e-commerce-part-2-integrating-snipcart-with-jekyll
[6]: https://gohugo.io/
[7]: https://snipcart.com/media/10148/hugo-static-site-generator.jpg
[8]: https://golang.org/
[9]: https://twitter.com/spf13
[10]: https://www.netlify.com/blog/2016/09/21/a-step-by-step-guide-victor-hugo-on-netlify/
[11]: https://snipcart.com/blog/integrating-snipcart-with-kirby-cms-to-enable-e-commerce
[12]: https://davidwalsh.name/introduction-static-site-generators
[13]: http://gohugo.io/overview/quickstart/
[14]: https://github.com/spf13/hugo/releases
[15]: http://gohugo.io/overview/introduction/
[16]: https://code.tutsplus.com/tutorials/make-creating-websites-fun-again-with-hugo-the-static-website-generator-written-in-go--cms-27319
[17]: http://themes.gohugo.io/
[18]: https://www.siteleaf.com/blog/jamstack-ecommerce/
[19]: https://www.contentful.com/blog/2016/02/10/snipcart-middleman-contentful/
[20]: https://docs.snipcart.com/getting-started/installation
[21]: https://docs.snipcart.com/configuration/product-definition
[22]: http://materializecss.com
[23]: https://docs.snipcart.com/getting-started/the-cart#adding-a-cart-summary
[24]: https://netlify.com
[25]: https://raw.githubusercontent.com/ChristopheDucamp/snipcart-hugo/master/static/images/Hugo-snipcart-netlify-deploiement.png
[26]: https://snipcart.com/media/10149/hugo-tutorial-klingon.jpg
[27]: https://raw.githubusercontent.com/ChristopheDucamp/snipcart-hugo/master/static/images/Aperçu-Snipcart-Hugo.png
[28]: http://baliff-cnythia-72262.netlify.com/
[29]: https://github.com/ChristopheDucamp/snipcart-hugo
[30]: https://testmysite.io
[31]: https://speedtracker.org/
[32]: https://www.keybits.net/post/publishing-workflow-for-teams-using-static-site-generators/
[33]: https://snipcart.com/blog/jamstack-clients-static-site-cms
[34]: https://twitter.com/home?status=Steps,%20Code%20Snippets%20%26%20Repo%3A%20Creating%20an%20Ecommerce%20Static%20Site%20w/%20%40spf13%27s%20Hugo%20%20http%3A//buff.ly/2moYM0U%20%23JAMstack%20%23staticweb%20%23gohugo


