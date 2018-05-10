---
title: Newbie sur la Jamstack...
date: 2016-12-20 11:56:00 +01:00
tags:
- jamstack
- jamstatic
- netlify
- Gandi
- Github
- DNS
- sous-domaine
- formation
---

{{< figure 
title="Roadmap JAMstack en bref"
src="/img/backend/roadmap-jamstatic.png"
attr="jamstatic - slack"
>}}

Sous le regard bienveillant de <span class="h-card">[Bertrand Keller](https://bertrandkeller.info/)</span>, je délaisse momentanément [mes recherches d'activation de certificats SSL sur Gandi](http://ducamp.me/2016-355)... 

Premiers pas dans l'interface-utilisateur du <abbr title="Content Delivery Network">CDN</abbr> [Netlify](http://netlify.com/) pour m'essayer à la [JAMstack](http://jamstack.org/fr/) en 2017.

>  La <dfn>JAMstack</dfn> est une manière idéale de bâtir des sites et des applications web performants, sécurisés et simples à mettre à jour.

> **JAM** signifie JavaScript, APIs and Markup (JavaScript, APIs et balisage). C'est l'association de technologies qui progresse le plus rapidement quand il s'agit de bâtir des sites et des applications web : plus de serveurs, hébergez tout votre partie cliente sur des CDNs et utilisez des APIs pour les parties dynamiques. (...)

Premier bénéfice escompté à cette heure : dire [adieu au protocole FTP](https://fr.wikipedia.org/wiki/File_Transfer_Protocol)...

## Paramétrage technique dans l'interface chez Gandi (nom de domaine)

Parcouru rapidement la [notice officielle de configuration d'un sous-domaine](https://www.netlify.com/docs/custom-domains/)

![Netlify-dns-records.png](/img/backend/netlify-dns-records.png)

À cette heure, j'ai simplement remplacé une ligne dans l'interface-utilisateur de réglages DNS chez Gandi  :

`christophe 10800 IN CNAME christopheducamp.github.io.` est devenu  `christophe IN A 104.198.14.52` 

Plus qu'à attendre la propagation des DNS (quelques heures) pour m'essayer à l'installation d'un SSL, aux plugins jekyll et ajouter les services workers dans Netlify.

Très envie d'apprendre ce monde merveilleux durant les fêtes.

Merci Bertrand.

<span id="CName"></span>


## Finalisation paramétrages DNS

(Edit) Tout étant parfaitement fonctionnel avec le pointage d'enregistrement A mentionné plus haut, je suis en train d'apprendre quelques [fondamentaux de sécurité et ce qu'il y a dans un CNAme](https://draftin.com/documents/974273?token=OPbK4C9757Jx6sDPqdgtyfPUo4LGvpq2Uy-T3u3dn9qToVbpDkf98RyNmu94LHmfQQQeOa0MuYBWs_JMTXgB87c). 

Parti pour un nouvel essai en cours de pointage d'un CName chez Gandi. Pour le sous-domaine `christophe`, je viens de remplacér la ligne de l'enregistrement A mentionnée plus haut par ce qui suit. 

![Gandi-CNAME-christophe.png](/img/backend/gandi-cname-christophe.png)

À valider dès propagation de DNS...


## Prochaines étapes

* [Apprendre à configurer un domaine apex personnalisé sur Netifly](https://draftin.com/documents/972632?token=pgFEOyn2g7cJbYPOqd30MQxLpb_Kj8_Kd9r2KuZvSuNDm7xMpl8VFfY5cfjMFXBVdwBG8PV99-80F4UJPFWbg6A)
* Apprendre quelques lignes de commande : [Netlify builds, deploys, and hosts your front end.](https://www.netlify.com/docs/)
* Essayer de construire un site avec GoHugo : [New to JAMstack ? How to make a site from A to Z](https://www.netlify.com/blog/2016/11/15/new-to-jamstack-how-to-make-a-site-from-a-to-z/)