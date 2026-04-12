---
title: "Pourquoi `node_modules` devient aussi énorme ?"
slug: "pourquoi-node-modules-est-gros"
description: "Une explication simple de la taille parfois absurde de `node_modules` dans l’écosystème Node.js."
longDescription: "Dans cet article, j’explique pourquoi le dossier `node_modules` devient si vite énorme : dépendances imbriquées, tooling moderne, duplication et fonctionnement de l’écosystème JavaScript."
tags: ["node_modules", "node.js", "npm", "pnpm", "javascript", "dépendances"]
readTime: 6
featured: true
timestamp: 2026-04-12
---

Si tu bosses un peu avec Node.js, il y a un moment où tu regardes ton projet et tu te demandes :

> pourquoi ce foutu dossier `node_modules` pèse déjà une demi-planète ?

Tu as installé trois dépendances, ton app fait deux pages, et pourtant tu te retrouves avec un dossier énorme rempli de milliers de fichiers.

Ce n’est pas ton imagination. C’est un comportement très classique de l’écosystème Node.

## La raison simple : tu n’installes jamais “juste un paquet”

Quand tu fais :

```bash
npm install un-paquet
```

ou :

```bash
pnpm add un-paquet
```

Tu n’installes quasiment jamais un seul truc.

Tu installes :

- le paquet principal
- ses dépendances
- les dépendances de ses dépendances
- et parfois encore plusieurs couches en dessous

Donc un petit paquet apparemment banal peut tirer derrière lui une grosse grappe de modules.

## L’écosystème JavaScript adore découper très fin

Le monde JavaScript a une tradition assez particulière :

- beaucoup de petits paquets
- beaucoup de micro-utilitaires
- beaucoup de briques ultra spécialisées

Parfois c’est bien.
Parfois c’est franchement excessif.

Résultat : un outil simple en apparence peut dépendre de dizaines, voire de centaines de paquets.

## Le tooling moderne rajoute encore une couche

Ce n’est pas seulement ton code métier qui installe des dépendances.

Très souvent, ton projet traîne aussi :

- un bundler
- un transpileur
- un linter
- un formatter
- des plugins
- des outils de test
- des outils de génération
- des adapters de build

Et chacun de ces outils a lui-même sa propre forêt de dépendances.

Donc même un projet “simple” peut embarquer un écosystème entier juste pour construire, vérifier et servir le site.

## Pourquoi il y a autant de fichiers

Parce que Node s’est construit historiquement autour d’une résolution de modules sur le système de fichiers.

Donc au lieu d’avoir un gros binaire compact ou quelques bibliothèques bien tassées, tu te retrouves souvent avec :

- énormément de dossiers
- énormément de petits fichiers
- énormément de sous-arborescences

Ce n’est pas très glamour, mais c’est comme ça que tout ça s’est construit.

## Et la duplication là-dedans ?

Elle joue aussi.

Selon le gestionnaire de paquets et selon les versions demandées, tu peux te retrouver avec plusieurs variantes proches d’une même dépendance.

C’est d’ailleurs une des raisons pour lesquelles **pnpm** est devenu populaire : il essaie de réduire ce gaspillage en s’appuyant sur un store global plus intelligent.

J’en parle plus en détail dans mon article sur [ce que `pnpm` change concrètement](/blog/pnpm-cest-quoi/).

## Pourquoi ça surprend autant au début

Parce que vu de l’extérieur, ça paraît absurde.

Tu te dis :

- mon site est petit
- mon code est court
- mon besoin est simple

et pourtant ton environnement local ressemble déjà à une petite décharge industrielle.

C’est le contraste qui choque.

## Est-ce que c’est forcément mauvais ?

Pas toujours.

Une partie de cette taille vient du fait que l’écosystème JavaScript repose sur énormément de briques réutilisées.

Le bon côté, c’est :

- beaucoup d’outils existent déjà
- tu peux assembler vite
- tu n’as pas à tout recoder toi-même

Le mauvais côté, c’est :

- beaucoup de poids
- beaucoup de complexité cachée
- beaucoup de surface de panne
- parfois des chaînes de dépendances absurdes

## Pourquoi il faut rester simple

C’est aussi pour ça que je préfère souvent des stacks sobres.

Moins tu ajoutes de tooling inutile, moins tu empiles de dépendances pour rien.

Si ton objectif est juste de faire un site propre, rapide et gratuit, tu n’as pas besoin d’une cathédrale d’outils autour.

J’en parle dans [ma stack recommandée pour lancer un site en 2026](/blog/site-propre-rapide-gratuit-2026/) et aussi dans mon article sur [pourquoi Markdown bat souvent un CMS pour un site simple](/blog/pourquoi-markdown-bat-un-cms/).

## La version courte

Si je résume brutalement :

- `node_modules` est énorme parce qu’un paquet en entraîne plein d’autres
- l’écosystème JavaScript adore les petites briques empilées
- le tooling moderne ajoute lui aussi beaucoup de dépendances
- la structure historique de Node multiplie les fichiers
- et certains outils comme `pnpm` essaient justement de rendre ça moins débile

Bref : **`node_modules` n’est pas énorme parce que ton projet est forcément gros. Il est énorme parce que l’écosystème Node empile énormément de dépendances, souvent pour de bonnes raisons… et parfois un peu n’importe comment.**

Si tu veux comprendre deux garde-fous utiles dans ce bazar, regarde aussi mes articles sur [pnpm](/blog/pnpm-cest-quoi/) et [les lockfiles](/blog/cest-quoi-un-lockfile/).
