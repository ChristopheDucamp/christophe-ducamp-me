---
title: "Archetypes"
date: 2017-07-20T17:39:13+02:00
draft: true
---

[source doc Hugo](https://gohugo.io/news/0-24/)

C'est la Renaissance des Archetypes 

    "Une fonctionnalité qui pourrait être le nom du prochain Indiana Jone mérite sa propre version," dit @bep.

Hugo gère maintenant les **fichiers archétypes sous forme de modèles Go**. Cela signifie que les problèmes de tri et de commentaires perdus relèvent du passé. Cela signifie également que vous devrez fournir toutes les valeurs, y compris le titre et la date. Mais cela ouvre également beaucoup de nouvelles fenêtres.

Un exemple fictif pour la section newsletter et le fichier ‘archetypes/newsletter.md’ :

```yaml
---
title: "{{ replace .TranslationBaseName "-" " " | title }}"
date: {{ .Date }}
draft: true
---

**Insérer ici le chapeau.**

<!--more-->

## Nouveaux Posts 

{{ range first 10 ( where .Site.RegularPages "Type" "cool" ) }}
* {{ .Title }}
{{ end }}
```

Et ensuite créez un nouveau post avec 

```bash
hugo new newsletter/les-derniers-trucs-cools.stuff.md
```

**Note :** le site ne sera construit que si le `.Site` est utilisé dans le fichier archetype, et cela peut **demander du temps pour les gros sites.**

**Truc chaud :** Si vous réglez la variable de configuration `newContentEditor` vers un éditeur sur votre `PATH`, l'article nouvellement créé sera ouvert.

Le *type d'archétype newsletter* au-dessus illustre les possibilités : La totalité du `.Site` Hugo et toutes les fonctionnalités de modèles d'Hugo peuvent être utilisés dans le fichier archetype.

**Aussi, Hugo supporte désormais les fichiers archetypes pour tous les formats de contenu, pas uniquement le markdown.**

## Notes

- Les fichiers archétypes ont besoin maintenant d'être complets, avec le `title` et la `date`.
- L'option `-f` (format) dans `hugo new` est retirée : Utilisez maintenant les fichiers achétypes comme tels.

## Améliorations 

-   * Support extension-less media types. The motivation behind this change is to support Netlify's `_redirects` files, so we can generate server-side redirects for the Hugo docs site. See [this commit](https://github.com/gohugoio/hugoDocs/commit/c1ab9894e8292e0a74c43bbca2263b1fb3840f9e) to see how we configured that. [0f40e1fa](https://github.com/gohugoio/hugo/commit/0f40e1fadfca2276f65adefa6d7d5d63aef9160a) [@bep](https://github.com/bep) [#3614](https://github.com/gohugoio/hugo/issues/3614)
  * Add `disableAliases` [516e6c6d](https://github.com/gohugoio/hugo/commit/516e6c6dc5733cdaf985317d58eedbc6ec0ef2f7) [@bep](https://github.com/bep) [#3613](https://github.com/gohugoio/hugo/issues/3613)
  * Support non-md files as archetype files [19f2e729](https://github.com/gohugoio/hugo/commit/19f2e729135af700c5d4aa06e7b3540e6d4847fd) [@bep](https://github.com/bep) [#3597](https://github.com/gohugoio/hugo/issues/3597)[#3618](https://github.com/gohugoio/hugo/issues/3618)
  * Identify extension-less text types as text [c43b512b](https://github.com/gohugoio/hugo/commit/c43b512b4700f76ac77f12d632bb030c3a241393) [@bep](https://github.com/bep) [#3614](https://github.com/gohugoio/hugo/issues/3614)
  * Add `.Site` to the archetype templates [662e12f3](https://github.com/gohugoio/hugo/commit/662e12f348a638a6fcc92a416ee7f7c2a7ef8792) [@bep](https://github.com/bep) [#1629](https://github.com/gohugoio/hugo/issues/1629)
  * Use archetype template as-is as a Go template [422057f6](https://github.com/gohugoio/hugo/commit/422057f60709696bbbd1c38c9ead2bf114d47e31) [@bep](https://github.com/bep)[#452](https://github.com/gohugoio/hugo/issues/452) [#1629](https://github.com/gohugoio/hugo/issues/1629)
  * Update links to new discuss URL [4aa12390](https://github.com/gohugoio/hugo/commit/4aa1239070bb9d4324d3582f3e809b702a59d3ac) [@bep](https://github.com/bep)
  

## Réparations 

  * Fix error handling for `JSON` front matter [fb53987a](https://github.com/gohugoio/hugo/commit/fb53987a4ff2acb9da8dec6ec7b11924d37352ce) [@bep](https://github.com/bep) [#3610](https://github.com/gohugoio/hugo/issues/3610)
  * Fix handling of quoted brackets in `JSON` front matter [3183b9a2](https://github.com/gohugoio/hugo/commit/3183b9a29d8adac962fbc73f79b04542f4c4c55d)[@bep](https://github.com/bep) [#3511](https://github.com/gohugoio/hugo/issues/3511)

  


