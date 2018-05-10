---
title: "Minimalisme"
date: 2017-08-30T16:20:32+02:00
draft: false
description: Changement de moteur. Migration de Jekyll vers Hugo.
---
> When you reduce things, the loading time is much lower. -- [Rafael Rozendaal](https://thecreativeindependent.com/people/rafael-rozendaal-on-streamlining-your-process/) 

Basé momentanément en Anjou avec une connexion edge bien pourrie. Concentré sur l'étude de ce bon [tutoriel](https://code.tutsplus.com/tutorials/make-creating-websites-fun-again-with-hugo-the-static-website-generator-written-in-go--cms-27319). Migration rapide de Jekyll vers GoHugo. Envie de minimalisme. Installation d'une *cabane numérique* pour travailler déconnecté. Et m'amuser à coder sur des tests rapides et sales.<!--more-->.

## Thèmes installés : Slim et After-Dark

[Slim](http://themes.gohugo.io/theme/slim) et After-Dark sont les deux thèmes que j'envisage pour réaliser des tests de performance ce sous-domaine motorisé par  [Hugo](http://gohugo.io/). 

## Déploiement Netlify 

La commande [`git clone` pour installer les thèmes](https://gohugo.io/themes/installing-and-using-themes/) n'étant pas supportée par Netlify, j'ai donc installé ces deux thèmes comme sous-modules Git. Pour plus d'informations, vous pouvez [lire la documentation Git pour les sous-modules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

La commande est similaire à celle de `git clone` : 

```bash
cd themes
git submodule add https://github.com/<CREATEURTHEME>/<NOMTHEME>
```

## Configuration Slim 

Ajouté des `params` à l'intérieur du fichier de configuration `config.toml` du site sous ce modèle :

```toml
[params]
  Subtitle = "Sous titre de votre site ou tagline"
  GithubID = "Votre ID Github"
  TwitterID = "Votre ID Twitter"
  AnalyticsID = "Your Google Analytics tracking code"
  DisqusShortname = "Votre pseudo disqus"
  Summary = true  # true or false
  Content = true  # true or false
  # si les deux sont sur true, le résumé est affiché.
  # FooterMsg = "Copyright tof 2017. Motorisé par Hugo."
```

si vous utilisez `config.yaml`, cela pourrait ressembler à ce qui suit :

```
params:
  Subtitle: "Your site's subtitle/tagline"
  GithubID: "Your Github ID"
  TwitterID: "Your Twitter ID"
  AnalyticsID: "Your Google Analytics tracking code"
  DisqusShortname: "Your Disqus shortname"
  Summary: true # takes true or false
  Content: false # takes true or false
  # if both are set to true, summary is shown
  # FooterMsg: "Custom footer message. Powered by Hugo."
```


## Focus 

- Temps de chargement sur une connexion edge
- lisibilité de nuit et en plein jour sur un écran de terminal mobile