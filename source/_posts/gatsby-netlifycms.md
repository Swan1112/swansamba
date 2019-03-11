---
title: TUTO Comment creer un site web statique avec Gatsby et NetlifyCMS
date: 2019-02-27 21:40:34
tags:
    netlifyCMS + Gatsby
---
Dans ce tuto nous allons creer un site statique avec Gatsby et un gestionnaire de contenu nommé Netlify CMS
```bash
gatsby new netlify-cms-tutorial https://github.com/gatsbyjs/gatsby-starter-hello-world

``` 

Maintenant on se deplace dans le nouveau dossier et on installle le plugin de gatsby pour Netlify CMS avec cette unique commande:

```bash
cd netlify-cms-tutorial && npm install --save netlify-cms gatsby-plugin-netlify-cms

``` 

Les plugins Gatsby sont enregistrés dans un fichier appelé gatsby-config.js à la racine du site. Créez ce fichier s'il n'y est pas déjà et ajoutez les éléments suivants pour enregistrer le plug-in Netlify CMS:

```bash

module.exports = {
  plugins: [`gatsby-plugin-netlify-cms`],
}

``` 


Enfin, vous devrez ajouter un fichier de configuration pour le CMS lui-même. Le plug-in que vous venez d'installer s'occupera de créer l'application Netlify CMS et de la générer dans «/admin/index.html».  Placer le fichier de configuration dans le même répertoire.



Toujours dans le répertoire racine vous devriez avoir un dossier «static». Il nous faut créer le fichier de configuration Netlify CMS dans le repertoire static / admin / config.yml. Une fois le dossier créer et le fichier créer , ajoutez ceci à votre nouveau config.yml:



```bash
backend:
  name: test-repo

media_folder: static/assets
public_folder: assets

collections:
  - name: blog
    label: Blog
    folder: blog
    create: true
    fields:
      - { name: path, label: Path }
      - { name: date, label: Date, widget: date }
      - { name: title, label: Title }
      - { name: body, label: Body, widget: markdown }

``` 

Ensuite, dans votre terminal, exécutez cette commande pour démarrer le serveur de développement Gatsby. 


```bash
gatsby develop

``` 

Une fois que le serveur est en cours d'exécution, il affichera l'adresse à ouvrir pour la  visualisation en local. C’est typiquement localhost: 8000. Ouvrez le lien dans un navigateur et vous devriez voir le texte «Hello World» dans le coin en haut à gauche. Maintenant, naviguez vers / admin / -( si votre site est à localhost: 8000, allez à localhost: 8000 / admin / ).

Vous devriez maintenant voir votre Netlify CMS. Vous avez défini une collection de «blogs» dans la configuration ci-dessus, vous pouvez donc créer de nouveaux blogs, mais Netlify CMS ne les stockera pas. Si vous actualisez vos modifications n'y figureront pas.


# Enregistrer dans un dépôt Git

Pour enregistrer votre contenu dans un repository Git, celui-ci doit être hébergé dans un service tel que GitHub

C’est également le bon moment pour considérer que Netlify CMS est conçu pour fonctionner en production et que le site fonctionne idéalement sur un déploiement continu (c'est à dire que chaque fois que le repository change, le site Web est reconstruit et redéployé. automatiquement). Lorsqu'il est utilisé en production, Netlify CMS et votre site Gatsby restent synchronisés, car votre site sera reconstruit après chaque modification.

