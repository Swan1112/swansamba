---
title: TUTO Creer un blog Rapide et performant avec Hexo
date: 2019-03-05 21:40:34

tags: 
    Hexo
    
---
Hexo est un Génerateur de blog statique simple, rapide et puissant propulsé par Node.js et NPM.

Pour ce tuto vous devez donc avoir installé la version LTS de [Node.js](https://nodejs.org/en/)
Ouvrez votre invité de commande et choisissez le chemin de votre dossier où va être installé votre site web :

```bash
npm install -g hexo
```

Vous allez créer un dossier avec tout ce qu'il faut à l'interieur avec cette commande :

```bash
hexo init nomdudossier
```
Ensuite vous entrez dans le dossier en question avec :

```bash
cd nomdudossier
```
Pour que les modules au fil de votre développement soient installés ou mis à jours automatiquement, utilisez ce code:

```bash
npm install
```

Les fichiers sont crées, maintenant si vous voulez utliser un thème, entrez dans le dossier themes avec cette commande:

```bash
cd themes
```
Puis Tapez "git clone" suivit du lien github de votre thème , exemple :

```bash
git clone https://github.com/ppoffice/hexo-theme-minos.git
```

Ensuite, il faut relier ce nouveau thème avec la configuration du site, pour cela entrez dans le fichier _config.yml et remplacez "theme: landscape" par :

```bash
theme: hexo-theme-minos
```
(le nom du thème correspond à son nom de dossier)

Finish ! il n'y a plus qu'à visualiser le site en local avec cette commande:

```bash
hexo server
```

