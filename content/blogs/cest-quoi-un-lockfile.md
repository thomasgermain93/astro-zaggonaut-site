---
title: "C’est quoi un lockfile, et pourquoi c’est important ?"
slug: "cest-quoi-un-lockfile"
description: "Explication simple des lockfiles : à quoi ils servent, pourquoi il faut les committer, et ce qu’ils évitent comme bugs."
longDescription: "Dans cet article, j’explique ce qu’est un lockfile (`package-lock.json`, `pnpm-lock.yaml`, etc.), pourquoi il est essentiel pour garder des installations reproductibles, et pourquoi le supprimer “pour repartir propre” est souvent une mauvaise idée."
tags: ["lockfile", "npm", "pnpm", "package manager", "node.js", "javascript"]
readTime: 5
featured: true
timestamp: 2026-04-12
---

Quand on débute avec Node.js, on voit souvent apparaître un fichier du genre :

- `package-lock.json`
- `pnpm-lock.yaml`
- `yarn.lock`

Et beaucoup de gens se disent :

> c’est quoi ce fichier moche, et est-ce que je peux le virer ?

Réponse courte : **non, ce n’est pas un déchet. Et oui, c’est important.**

## Un lockfile, ça sert à figer les versions réellement installées

Le fichier `package.json` dit en gros :

- de quelles dépendances ton projet a besoin
- avec quelles plages de versions

Mais il ne suffit pas toujours à garantir que tout le monde installe exactement la même chose.

Le lockfile, lui, enregistre beaucoup plus précisément :

- les versions résolues
- les sous-dépendances
- l’arbre d’installation réel

Autrement dit : **il fixe l’état exact de ce qui a été installé**.

## Pourquoi c’est important

Parce que sinon, deux personnes peuvent avoir :

- le même code source
- le même `package.json`
- mais pas exactement les mêmes dépendances installées

Et là, bonjour les bugs débiles du style :

- “chez moi ça marche”
- “chez toi ça casse”
- “en CI ça plante”

Le lockfile réduit précisément ce genre de merde.

## Il sert aussi pour les déploiements

Ce n’est pas juste utile en local.

Quand ton projet est buildé en CI ou déployé sur une plateforme, le lockfile aide à retrouver le même état de dépendances.

Donc si tu veux un projet :

- stable
- reproductible
- prévisible

il vaut mieux le garder et le committer.

## Pourquoi il y a plusieurs noms

Parce que chaque gestionnaire de paquets a le sien :

- `npm` → `package-lock.json`
- `pnpm` → `pnpm-lock.yaml`
- `yarn` → `yarn.lock`

Le principe reste le même.

D’ailleurs, si tu ne vois pas encore bien la différence entre `npm`, `npx` et `pnpm`, j’ai aussi des articles séparés sur [`npx`](/blog/npx-cest-quoi/) et [pnpm](/blog/pnpm-cest-quoi/).

## Pourquoi le supprimer “pour repartir propre” est souvent une mauvaise idée

C’est une habitude qu’on voit souvent :

> supprime le lockfile et réinstalle tout

Parfois, oui, ça peut aider dans un cas bien précis.
Mais comme réflexe général, c’est souvent une mauvaise idée.

Pourquoi ? Parce que tu perds justement :

- la reproductibilité
- la stabilité
- la traçabilité de l’état précédent

Tu ne “nettoies” pas forcément le projet.
Tu changes potentiellement plein de versions d’un coup, parfois sans t’en rendre compte.

## Le lockfile n’est pas là pour faire joli

Il est là pour éviter l’aléatoire.

Et dans un écosystème où une dépendance peut elle-même dépendre de 40 autres trucs, ce n’est pas un luxe.

C’est aussi pour ça que les projets un peu sérieux imposent souvent un gestionnaire précis, par exemple `pnpm`, avec son lockfile propre.

## Le lien avec la stack simple

Plus ton setup est simple, plus tu veux garder de la stabilité là où c’est utile.

Si tu construis un site moderne avec une stack légère, un repo Git propre et un hébergement simple, le lockfile fait partie des petits fichiers moches mais vraiment utiles.

J’en parle dans [ma stack simple pour lancer un site en 2026](/blog/site-propre-rapide-gratuit-2026/).

## La version courte

Si je résume brutalement :

- le `package.json` dit ce que tu veux installer
- le lockfile dit ce qui a été réellement installé
- il rend les installations plus reproductibles
- il limite les écarts entre machines et entre déploiements
- il faut généralement le committer
- et le supprimer “pour faire propre” est souvent une idée moyenne

Bref : **un lockfile, c’est un garde-fou contre le chaos discret des dépendances.**

Et si tu veux comprendre pourquoi ce chaos existe déjà avant même de parler de lockfile, tu peux lire aussi [pourquoi `node_modules` devient aussi énorme](/blog/pourquoi-node-modules-est-gros/).
