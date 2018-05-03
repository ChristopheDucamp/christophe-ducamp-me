---
title: "Démarrer Avec Hugo"
date: 2017-08-30T07:38:19+02:00
draft: true
---

J'ai donc abandonné définitivement [Jekyll](https://jekyllrb.com/) pour me lancer dans le grand bain de la JAMstack avec [Hugo](https://gohugo.io), le générateur de site statique écrit en [Go](https://golang.org). Go est un langage de programmation rapide développé par Google.

Nouveau tournant avec l'intention de construire un nouveau portfolio plus en image, pratique et raffiner quelques compétences de développement web.

## Objectifs

   * Créer un portfolio pour présenter mes travaux
   * Revenir sur un blog pour noter mes progrès et aider les autres en cours de route
   * Apprendre la conception SCSS
   * Apprendre à personnaliser un thème Hugo

<!--

## Créer un portfolio


The portfolio has been created and published in place of my old portfolio site. Currently, projects are displayed under the “Work” section on the index page. The index page was constructed as a one-page template to display a hero header, gallery of web projects, a list of the 10 latest blog posts, and a contact form.
-->

## Créer un Blog
<!--
The blog post links on the index page lead to their own individual pages. The majority of the blog was based off of the [Hugo Black and Light Theme](https://github.com/davidhampgonsalves/hugo-black-and-light-theme) by David Hamp-Gonsalves. Overall, it was a well-constructed, minimalist, text-only theme without any scripts or clutter. The blog has been slightly redesigned but there is a bit more customization work to be done.
-->
## Utiliser SCSS

Mon premier défi majeur est d'imaginer comment utiliser [SCSS](http://sass-lang.com/). 

Ressource : lire Dan Bahrami, [Building a production website with Hugo and GulpJS](http://danbahrami.io/articles/building-a-production-website-with-hugo-and-gulp-js/). 

<!-- This also marked my first exposure to [Node.js](https://nodejs.org/en/).
-->

## Designer & Distribuer un Thème Hugo

Même si le thème que j'utilise n'est pas encore parfait, il me suffit pour l'utilisation et la publication, mais il y a un moyen de l'optimiser et/ou d'en créer un dès que je me serai familiarisé avec la syntaxe. 

<!-- 
While the theme I’ve constructed is fine to publish now and use myself, there is a ways to go to clean it up and optimize it before distributing to the Hugo community. This will be the most challenging objective that I still need to complete and requires more studying of Hugo and the correct syntax. However, I’m very close to finishing the design portion of the theme!
-->

# Workflow Hugo

Le workflow Hugo est vraiment simple. Ceci est le workflow que j'utilise pour mettre à jour ce blog et mon futur portfolio.

Dans mon dossier projet Hugo, le dossier `public/` est généré avec tous les fichiers statiques une fois que je lance `hugo` dans le terminal.

## Purger et Servir

Pour générer un dossier `public/`, retirez simplement l'existant et lancez le serveur. Toutes les mises à jour effectuées sur votre contenu sont désormais disponibles dans le nouveau dossier  `public/` et visibles sur le serveur live.

Assurez-vous de toujours retirer le vieux dossier `public/`, sinon Hugo continuera à mettre à jour les fichiers existants et ajoutera de nouveaux fichiers sans avoir retiré les vieux fichiers inutiles. Inutile de vous encombrer et créer la confusion
    
    $ rm -rf public/
    $ hugo server --verbose
    

### LiveReload

One of my favorite features in Hugo so far? LiveReload. The Hugo server automatically watches your project folder for changes and refreshes your browser when any new changes are made while editing, creating, or deleting files.

This is great for development when you can make changes in your text editor and immediately see them occur in your browser window.

If you want to disable LiveReload:
    
    $ hugo server --disableLiveReload
    

## Gulp Pipeline

When making any styling changes or designing themes, I use a Gulp pipeline to compile my SCSS files into compressed CSS files that are then rendering into the `public/` folder appropriately. Besides compiling and compressing style files, my gulpfile also runs a task that minifies my JavaScript files. Dan Bahrami has a [great guide](http://danbahrami.io/articles/building-a-production-website-with-hugo-and-gulp-js/) that includes setting up a Gulp pipeline and assigning Gulp tasks to watch for changes in style folders.

To get the Gulp pipeline going after I start the Hugo server, I simply type:
    
    $ gulp
    

## Nouveau Contenu

Creating new content in the project folder is also very simple. For example, I created this page as a markdown file inside of `content/blog/`:
    
    $ hugo new blog/hugo-workflow.md
    

So far I’ve been enjoying writing blog posts in markdown.

## Déploiement Hugo

Pour déployer Hugo, j'utilise en ce moment 

<!--
 [hugodeploy](https://github.com/mindok/hugodeploy), a simple FTP/SFTP deployment tool built in Go. Content inside of `public/` is effortlessly uploaded to my website’s root folder on my shared webhost account with two simple commands:
    
    $ hugodeploy preview
    $ hugodeploy push
-->    

A neat extra feature of hugodeploy is the minification of CSS, HTML, JavaScript, JSON, and XML files upon deployment. While this option can be turned off, it does help with file size and site speed if you’re not already minifying your static files.

### Rsync Process

An alternative deployment method I was thinking about using and may try out down the line is using rsync. Andrew Codispoti detailed the steps to [setting up an rsync process](http://www.andrewcodispoti.com/deploy-process/) that can deploy updates when committing and pushing with git.

### Nettoyer le Cache

I use CloudFlare as my DNS to cache my static files and help serve them faster around the world. When deploying, I sometimes find that I’ll need to clear CloudFlare’s caches in order to serve up freshly update files. As a little shortcut to constantly going to the CloudFlare site and manually clearing the cache, I created a [shell script that clears the cache](https://tomanistor.com/blog/shell-script-to-clear-cloudflare-cache) after deployment when I call it in the terminal with: `cloudclear`.

## Conclusion

All in all, my Hugo workflow is short and sweet. A typical update and publication to the live site can look like this:
    
    $ rm -rf public
    $ hugo
    $ hugodeploy preview
    $ hugodeploy push
