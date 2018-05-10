---
title: "Automatisation Blog Statique"
date: 2018-05-10T15:33:06+02:00
draft: true
---

Comme je l'ai écrit dans le passé [ce blog est désormais alimenté par Hugo](https://jnjosh.com/posts/goodbye-octopress-hello-hugo/) -un générateur de site statique. C'est génial et tout, mais cela limite vraiment quand je peux écrire des messages. Quelque chose faisant tourner Hugo doit construire le site et cette sortie doit être publiée quelque part. J'ai fait quelques petites choses pour rendre ce processus plus automatique.

## Écrire des Posts sur mon MacBook Pro

Tout d'abord, j'avais besoin de faciliter la création d'un nouveau post. [Mon thème](https://github.com/jnjosh/internet-weblog) a trois types de contenu et il n'est pas facile de se souvenir de la commande à faire pour produire le bon type de post. Pour résoudre cela j'ai créé quelques script simples bash pour aider. 
    
    function newmicropost() {
        local date=`date +%Y-%m-%d-%H%M%S`
        local file="microposts/${date}.md"
        hugo new ${file} | cut -d ' ' -f 1 | xargs subl 
    }
    
    // $1 The name of the file to create
    function newpost() {
        hugo new "posts/$1.md" | cut -d ' ' -f 1 | xargs subl
    }
    
    // $1 The name of the file to create
    function newphotopost() {
    	hugo new "photos/$1.md" | cut -d ' ' -f 1 | xargs subl
    }

This is really great when I want to publish a [Micro.blog](https://micro.blog) post about some idea that pops up while working. I’m already in the terminal normally so jumping to my blog directory and typing `newmicropost` is pretty quick.

C'est vraiment génial quand je veux publier un article [Micro.blog](https://micro.blog) sur une idée qui surgit en travaillant. Je suis déjà dans le terminal normalement en train de sauter dans mon répertoire de blogs et taper `newmicropost` est assez rapide.

## Writing Posts on my iPad or iPhone

This is a bit more difficult and I’m still working out how to best do this. The biggest key was to not have to run Hugo myself. Offloading that task (and hosting) to [Netlify](https://www.netlify.com) powered by a Github webhook means I can create and publish from any device simply by commiting to Github.

An app like [Working Copy](https://workingcopyapp.com) or [Clone](http://clone.hammockdistrict.com) makes this possible. It’s admittedly a bit of a chore to post from the iPhone because you have to not only create the markdown file in the right place, but also create the correct front matter so that Hugo can properly generate your page. My current process is to write a post in [Ulysses](https://ulyssesapp.com), where I have a document with all the expected front matter. Then when I am ready to publish I copy that over to Working Copy and push a commit.

I’d like this all to be better. I’m really interested in what others have done here. I love having a static website, but the nature of it puts a pretty nasty obstacle in my way.

C'est un peu plus difficile et je travaille encore sur la meilleure façon de le faire. La plus grande clé était de ne pas avoir à gérer Hugo moi-même. La délégation de cette tâche (et de l'hébergement) à [Netlify](https://www.netlify.com) alimenté par un webhook Github signifie que je peux créer et publier à partir de n'importe quel appareil simplement en validant Github.

Une application comme [Working Copy](https://workingcopyapp.com) ou [Clone](http://clone.hammockdistrict.com) rend cela possible. Il est vrai que c'est un peu une corvée à publier sur l'iPhone parce que vous devez non seulement créer le fichier markdown au bon endroit, mais aussi créer le Front Matter afin que Hugo puisse correctement générer votre page. Mon processus actuel consiste à écrire un post dans [Ulysses](https://ulyssesapp.com), où j'ai un document avec toutes les informations attendues. Puis, quand je suis prêt à publier, je copie sur Working Copy et j'appuie sur un commit.

J'aimerais que tout cela soit meilleur. Je suis vraiment intéressé par ce que les autres ont fait ici. J'aime avoir un site Web statique, mais la nature de celui-ci met un obstacle assez désagréable sur mon chemin.
