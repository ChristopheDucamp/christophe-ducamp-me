---
title: "Going Offline"
date: 2018-04-29T09:26:26+02:00
publishdate: "2018-04-29"
lastmod: "2018-04-29"
description: ""
toc: true
draft: true
slug: going-offline
categories: ["technologie"]
tags: [web]
images: [
  ""
] # remplace l'image open graph du site
---

Lecture [Going Offline](https://alistapart.com/article/going-offline) de [Jeremy Keith](https://adactio.com/)
<!--more-->

L'intention serait d'apprendre ce qu'est un service worker, les concepts et m'essayer à un premier usage sur ce site web "bac à sable" 

![Le service workers indique au navigateur de faire quelque chose avant qu'il n'envoie la requête pour faire la queue pour URL](https://monosnap.com/image/7JKIeON0wDtyZJNf1NQsmLVh3vT4Sa.png)


1. Commencé par créer un fichier JavaScript blanc appelé `serviceworker.js` sauvegardé à la racine du site.
2. Ajouté une ligne `<link rel="serviceworker" href="/serviceworker.js">` dans l'en-tête fichier `ìndex.html`
3. Posé la ligne `<script>
navigator.serviceWorker.register('/serviceworker.js');
</script>` en bas du fichier index.html
