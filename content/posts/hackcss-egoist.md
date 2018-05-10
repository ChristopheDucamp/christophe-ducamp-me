---
title: "hackcss"
date: 2017-09-01T19:21:12+02:00
publishdate: 2017-09-01
lastmod: 2017-09-02
draft: true
description: Un framework css vraiment tout simple
toc: true
categories: ["technologie"]
tags: [100daysofcode, css, framework]
images: [
  ""
] # remplace l'image open graph du site
---
<!-- octocat svg placé en haut à droite -->
<a href="https://github.com/ChristopheDucamp/christophe.ducamp.me/edit/master/content/post/hackcss-egoist.md" alt="éditez cette page sur mon repo github"><svg width="80" height="80" viewBox="0 0 250 250" style="fill:#151513; color:#fff; position: absolute; top: 0; border: 0; right: 0;"><path d="M0,0 L115,115 L130,115 L142,142 L250,250 L250,0 Z"></path><path d="M128.3,109.0 C113.8,99.7 119.0,89.6 119.0,89.6 C122.0,82.7 120.5,78.6 120.5,78.6 C119.2,72.0 123.4,76.3 123.4,76.3 C127.3,80.9 125.5,87.3 125.5,87.3 C122.9,97.6 130.6,101.9 134.4,103.2" fill="currentColor" style="transform-origin: 130px 106px;" class="octo-arm"></path><path d="M115.0,115.0 C114.9,115.1 118.7,116.5 119.8,115.4 L133.7,101.6 C136.9,99.2 139.9,98.4 142.2,98.6 C133.8,88.0 127.5,74.4 143.8,58.0 C148.5,53.4 154.0,51.2 159.7,51.0 C160.3,49.4 163.2,43.6 171.4,40.1 C171.4,40.1 176.1,42.5 178.8,56.2 C183.1,58.6 187.2,61.8 190.9,65.4 C194.5,69.0 197.7,73.2 200.1,77.6 C213.8,80.2 216.3,84.9 216.3,84.9 C212.7,93.1 206.9,96.0 205.4,96.6 C205.1,102.4 203.0,107.8 198.3,112.5 C181.9,128.9 168.3,122.5 157.7,114.1 C157.9,116.9 156.7,120.9 152.7,124.9 L141.0,136.5 C139.8,137.7 141.6,141.9 141.8,141.8 Z" fill="currentColor" class="octo-body"></path></svg></a>

Comme beaucoup de hackers, j'adore la lisibilité du [markdown](https://daringfireball.net/projects/markdown/). L'idée qui me botte avec le thème Afterdark (utilisé à cette heure pour le site), c'est de disposer d'une petite cabane personnelle numérique tout markdown pour produire des contenus web valides structurellement, faciles à lire et à copier. 
Le thème "dark" est aussi conçu pour protéger les yeux en basse lumière. 

Ce site web dark utilise le thème After-dark. Un thème reposant sur le framework "hack.css" disponible sur <https://hackcss.egoist.moe/>. 

Tour d'horizon.

### Alternatives couleurs 

Les modes [dark-grey](https://hackcss.egoist.moe/dark-grey.html), [solarized-dark](https://hackcss.egoist.moe/solarized-dark.html) et [standard](https://hackcss.egoist.moe/standard.html) sont aussi disponibles !


## Utiliser hackcss 

`hack.css` est parfait pour la page d'accueil de vos projets open-source. Il s'installe en lançant `npm install -S hack` et vous le chargez avec votre pré-processeur css préféré.

Vous pouvez aussi hot-linker l'url du fichier css.
La dernière étape est d'ajouter la classe `.hack` à votre élément `body`.


```html
<!-- requis dans tous les modes -->
<link rel="stylesheet" href="/path/to/hack.css">

<!-- mode markdown -->
<body class="hack"></body>

<!-- mode standard -->
<link rel="stylesheet" href="/path/to/standard.css">
<body class="standard"></body>

<!-- mode dark -->
<link rel="stylesheet" href="/path/to/dark.css">
<body class="hack dark"></body>

```


## Guide Pratique 

### Basique

Utilisez `.container` pour centraliser tout le contenu principal.

Utilisez **[flexbox](https://developer.mozilla.org/fr/docs/Web/CSS/Disposition_des_bo%C3%AEtes_flexibles_CSS/Utilisation_des_flexbox_en_CSS)** pour produire les layouts.

```html
<div class="exemple">
	<div class="grid grid-example">
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	</div>
	<div class="grid grid-example">
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	  <div class="cell -8of12">
		<div class="content">8</div>
	  </div>
	</div>
	<div class="grid grid-example">
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	</div>
	</div>
```


<div class="exemple" style="border: 1px solid red">
	<div class="grid grid-exemple">
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	</div>
	<div class="grid grid-exemple">
	  <div class="cell -4of12">
		<div class="content">4</div>
	  </div>
	  <div class="cell -8of12">
		<div class="content">8</div>
	  </div>
	</div>
	<div class="grid grid-exemple">
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	  <div class="cell">
		<div class="content">1</div>
	  </div>
	</div>
  </div>

#### modificateurs de `.grid`

* Pour aligner les items avec **align-items**
* **-top**: vers le haut
* **-middle**: vers le milieu
* **-bottom**: vers le bas
* **-stretch**: étirer les items
* **-baseline**: vers la base line
* Pour mettre en forme les contenus avec **justify-content**
* **-left**: vers la gauche
* **-center**: vers le centre
* **-right**: vers la droite
* **-between**: ajouter des espaces entre les items
* **-around**: ajouter des espaces autour des items

#### modificateurs de `.cell` 

* **-1of12**: Set item width to 8.3% of parent
* **-2of12**: Set item width to 16.7% of parent
* **-3of12**: Set item width to 25% of parent
* **-4of12**: Set item width to 33% of parent
* **-5of12**: Set item width to 41.7% of parent
* **-6of12**: Set item width to 50% of parent
* **-7of12**: Set item width to 58.3% of parent
* **-8of12**: Set item width to 66.7% of parent
* **-9of12**: Set item width to 75% of parent
* **-10of12**: Set item width to 83.3% of parent
* **-11of12**: Set item width to 91.7% of parent
* **-12of12**: Set item width to 100% of parent

### Composants 

#### élément hr 
<hr>

#### Liste

  <ul>
	<li>foo
	  <ul>
		<li>sous foo</li>
		<li>sous bar</li>
		<li>sous baz</li>
	  </ul>
	</li>
	<li>bar</li>
	<li>baz</li>
  </ul>
 
 #### Blockquote 
  
<blockquote>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptates quis cumque similique voluptas facilis fugit inventore odit, quidem et ab, quos, blanditiis iure! Ipsum nostrum corrupti architecto fugit, culpa expedita.</blockquote>

#### Formulaire 
```html
<form class="form">
  <fieldset class="form-group">
    <label for="username">USERNAME:</label>
    <input id="username" type="text" placeholder="type your name..." class="form-control">
  </fieldset>
  <fieldset class="form-group">
    <label for="email">EMAIL:</label>
    <input id="email" type="email" placeholder="" class="form-control">
  </fieldset>
  <fieldset class="form-group">
    <label for="country">COUNTRY:</label>
    <select id="country" class="form-control">
      <option>China</option>
      <option>U.S.</option>
      <option>U.K.</option>
      <option>Japan</option>
    </select>
  </fieldset>
  <fieldset class="form-group form-textarea">
    <label for="message">MESSAGE:</label>
    <textarea id="message" rows="5" class="form-control"></textarea>
  </fieldset>
  <div class="form-actions">
    <button type="button" class="btn btn-primary btn-block">Submit</button>
  </div>
</form>
```


<form class="form">
  <fieldset class="form-group">
    <label for="username">Nom d'Utilisateur:</label>
    <input id="username" type="text" placeholder="type your name..." class="form-control">
  </fieldset>
  <fieldset class="form-group">
    <label for="email">e-mail :</label>
    <input id="email" type="email" placeholder="" class="form-control">
  </fieldset>
  <fieldset class="form-group">
    <label for="country">Pays:</label>
    <select id="country" class="form-control">
      <option>Chine</option>
      <option>U.S.</option>
      <option>U.K.</option>
      <option>Japon</option>
    </select>
  </fieldset>
  <fieldset class="form-group form-textarea">
    <label for="message">MESSAGE:</label>
    <textarea id="message" rows="5" class="form-control"></textarea>
  </fieldset>
  <div class="form-actions">
    <button type="button" class="btn btn-primary btn-block">Envoyer</button>
  </div>
</form>

#### Formulaire Admin
  
  <form class="form">
	<fieldset class="form-group form-success">
	  <label for="username2">Nom Utilisateur:</label>
	  <input id="username2" type="text" placeholder="entrez votre nom..." class="form-control">
	</fieldset>
	<fieldset class="form-group form-warning">
	  <label for="age">AGE:</label>
	  <input id="age" type="text" placeholder="" class="form-control">
	</fieldset>
  </form>
  
```html
<form class="form">
	<fieldset class="form-group form-success">
	  <label for="username2">Nom Utilisateur:</label>
	  <input id="username2" type="text" placeholder="entrez votre nom..." class="form-control">
	</fieldset>
	<fieldset class="form-group form-warning">
	  <label for="age">AGE:</label>
	  <input id="age" type="text" placeholder="" class="form-control">
	</fieldset>
  </form>
```
  
##### Bloc Aide 

```html
<form class="form">
 <fieldset class="form-group form-success">
   <label for="phone">N° Téléphone :</label>
     <input id="phone" type="text" value="+86 180 800 8000" placeholder="" class="form-control">
	    <div class="help-block">Dans ce format: +86 xxx xxx xxxxx</div>
  </fieldset>
  <fieldset class="form-group form-error">
    <label for="email3">e-mail :</label>
      <input id="email3" type="email" placeholder="" class="form-control">
  </fieldset>
</form>
```

<form class="form">
 <fieldset class="form-group form-success">
   <label for="phone">N° Téléphone :</label>
     <input id="phone" type="text" value="+86 180 800 8000" placeholder="" class="form-control">
	    <div class="help-block">Dans ce format: +86 xxx xxx xxxxx</div>
  </fieldset>
  <fieldset class="form-group form-error">
    <label for="email3">e-mail :</label>
      <input id="email3" type="email" placeholder="" class="form-control">
  </fieldset>
</form>
  

#### Tableau

```html
<table>
  <thead>
    <tr>
      <th>éditeur</th>
      <th>vitesse</th>
      <th>extension</th>
      <th>interface</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>sublime</td>
     <td>90</td>
     <td>80</td>
     <td>70</td>
    </tr>
    <tr>
      <td>atom</td>
      <td>60</td>
      <td>85</td>
      <td>80</td>
    </tr>
    <tr>
      <td>vscode</td>
      <td>80</td>
      <td>65</td>
      <td>60</td>
    </tr>
  </tbody>
</table>
```

<table>
  <thead>
    <tr>
      <th>éditeur</th>
      <th>vitesse</th>
      <th>extension</th>
      <th>interface</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>sublime</td>
     <td>90</td>
     <td>80</td>
     <td>70</td>
    </tr>
    <tr>
      <td>atom</td>
      <td>60</td>
      <td>85</td>
      <td>80</td>
    </tr>
    <tr>
      <td>vscode</td>
      <td>80</td>
      <td>65</td>
      <td>60</td>
    </tr>
  </tbody>
</table>


#### Barre de Progression

```html
<!-- avec seulement une flèche -->
<div class="progress-bar">
  <div class="progress-bar-filled" style="width: 42%"></div>
</div>

<!-- avec un pourcentage s'affichant au-dessus de la flèche -->
<div class="progress-bar progress-bar-show-percent">
  <div class="progress-bar-filled" style="width: 42%" data-filled="Chargement 42%"></div>
</div>
```

<!-- avec seulement une flèche -->
<div class="progress-bar">
  <div class="progress-bar-filled" style="width: 40%"></div>
</div>

<!-- avec un pourcentage s'affichant au-dessus de la flèche -->
<div class="progress-bar progress-bar-show-percent">
  <div class="progress-bar-filled" style="width: 40%" data-filled="Chargement 42%"></div>
</div>

#### Boutons 
 
```html
<button class="btn btn-default">Default</button>
<button class="btn btn-primary">Primary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-error">Error</button>

<button class="btn btn-primary btn-ghost">Ghost Button</button>

<button class="btn btn-primary btn-block">Block Level Button</button>
```  

<button class="btn btn-default">Default</button>
<button class="btn btn-primary">Primary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-error">Error</button>

<button class="btn btn-primary btn-ghost">Bouton Ghost </button>

<button class="btn btn-primary btn-block">Bouton Niveau Bloc</button>

#### Groupe de Boutons 

  <div class="exemple">
	  <div class="btn-group">
	    <button class="btn btn-success btn-ghost">Gauche</button>
	    <button class="btn btn-success btn-ghost">Milieu</button>
	    <button class="btn btn-success btn-ghost">Droite</button>
	  </div>
  </div>

```html
 <div class="exemple">
	  <div class="btn-group">
	    <button class="btn btn-success btn-ghost">Gauche</button>
	    <button class="btn btn-success btn-ghost">Milieu</button>
	    <button class="btn btn-success btn-ghost">Droite</button>
	  </div>
  </div>
```
#### Card

```html
<div class="card">
  <header class="card-header">titre</header>
  <div class="card-body">
    <div class="inner">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Expedita, quas ex vero enim in doloribus officiis ullam vel nam esse sapiente velit incidunt. Eaque quod et, aut maiores excepturi sint.</div>
  </div>
</div>
```

<div class="card">
  <header class="card-header">titre</header>
  <div class="card-body">
    <div class="inner">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Expedita, quas ex vero enim in doloribus officiis ullam vel nam esse sapiente velit incidunt. Eaque quod et, aut maiores excepturi sint.</div>
  </div>
</div>

<br>


#### Alertes 
```html
<div class="alert alert-success">Message success</div>
<div class="alert alert-info">Message info</div>
<div class="alert alert-warning">Message warning</div>
<div class="alert alert-error">Message error</div>
```

<div class="alert alert-success">Message success</div>
<div class="alert alert-info">Message info</div>
<div class="alert alert-warning">Message warning</div>
<div class="alert alert-error">Message error</div>  

#### Menu 

```html
<div class="menu">
   <a class="menu-item">
     item #1 <div class="pull-right">»</div>
   </a>
   <a class="menu-item active">
     item #2 <div class="pull-right">»</div>
   </a>
   <a class="menu-item">
     item #3 <div class="pull-right">»</div>
   </a>
 </div>
 ```
 
 <div class="menu">
   <a class="menu-item">
     item #1 <div class="pull-right">»</div>
   </a>
   <a class="menu-item active">
     item #2 <div class="pull-right">»</div>
   </a>
   <a class="menu-item">
     item #3 <div class="pull-right">»</div>
   </a>
 </div>
 
 #### Media
 
 C'est utile pour afficher une liste d'items, comme la timeline Twitter.
 
 
 ```html
 <!-- alignement à gauche -->
<div class="media">
  <div class="media-left">
    <div class="avatarholder">e</div>
  </div>
  <div class="media-body">
    <div class="media-heading">EGOIST @egoist</div>
    <div class="media-content">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga vel, voluptates, doloremque nesciunt illum est corrupti nostrum expedita adipisci dicta vitae? Eveniet maxime quibusdam modi molestias alias et incidunt est.</div>
  </div>
</div>

<!-- alignement à droite -->
<div class="media">
  <div class="media-body">
    <div class="media-heading">EGOIST @egoist</div>
    <div class="media-content">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga vel, voluptates, doloremque nesciunt illum est corrupti nostrum expedita adipisci dicta vitae? Eveniet maxime quibusdam modi molestias alias et incidunt est.</div>
  </div>
  <div class="media-right">
    <div class="avatarholder">e</div>
  </div>
</div>
```

<div class="media">
  <div class="media-left">
    <div class="avatarholder">e</div>
  </div>
  <div class="media-body">
    <div class="media-heading">EGOIST @egoist</div>
    <div class="media-content">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga vel, voluptates, doloremque nesciunt illum est corrupti nostrum expedita adipisci dicta vitae? Eveniet maxime quibusdam modi molestias alias et incidunt est.</div>
  </div>
</div>

<!-- alignement à droite -->
<div class="media">
  <div class="media-body">
    <div class="media-heading">EGOIST @egoist</div>
    <div class="media-content">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga vel, voluptates, doloremque nesciunt illum est corrupti nostrum expedita adipisci dicta vitae? Eveniet maxime quibusdam modi molestias alias et incidunt est.</div>
  </div>
  <div class="media-right">
    <div class="avatarholder">e</div>
  </div>
</div>

#### Loading 

hack.css vous donne un élément loading par défaut, mais vous pourrez en trouver d'autres sur [CSS-only loaders](https://www.pexels.com/blog/css-only-loaders/).

```
<div class="loading"></div>

<button class="btn btn-info btn-ghost">
  Chargement en cours&hellip;
  <span class="loading"></span>
</button>

<div class="alert alert-info">
  <span class="loading"></span>
  Chargement dans une boîte d'alerte&hellip;
</div>
```

<div class="loading"></div>

<button class="btn btn-info btn-ghost">
  Chargement en cours&hellip;
  <span class="loading"></span>
</button>

<div class="alert alert-info">
  <span class="loading"></span>
  Chargement dans une boîte d'alerte&hellip;
</div>
