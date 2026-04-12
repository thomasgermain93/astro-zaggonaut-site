---
title: "pnpm, c’est quoi exactement ?"
slug: "pnpm-cest-quoi"
description: "Explication simple de pnpm : pourquoi il existe, ce qui le distingue de npm, et dans quels cas il est intéressant."
longDescription: "Dans cet article, j’explique à quoi sert pnpm, pourquoi certains projets l’imposent, ce qu’il change par rapport à npm, et pourquoi ce n’est pas juste une mode de plus dans l’écosystème JavaScript."
tags: ["pnpm", "npm", "node.js", "javascript", "package manager"]
readTime: 5
featured: false
timestamp: 2026-04-12
---

Quand on bosse avec Node.js, on croise vite trois noms qui reviennent tout le temps : **npm**, **yarn** et **pnpm**.

Si tu tombes sur un projet qui te répond un truc du genre :

```bash
Only pnpm is supported on this project
```

ça peut être un peu agaçant. Et la première réaction est souvent : **ok, mais pourquoi encore un autre gestionnaire de paquets ?**

La réponse courte : **pnpm sert à installer les dépendances Node de manière plus efficace, plus propre et souvent plus rapide que npm classique.**

## Déjà, c’est quoi un gestionnaire de paquets ?

Un gestionnaire de paquets, c’est l’outil qui s’occupe de :

- télécharger les dépendances d’un projet
- les enregistrer dans le projet
- gérer les versions
- lancer certains scripts

Dans le monde Node, `npm` est l’outil historique. `pnpm` fait globalement le même boulot, mais avec une approche différente.

Si tu veux voir où ce genre d’outils s’insère dans une stack web simple et peu coûteuse, j’en parle aussi dans [cet article sur la stack que je recommande en 2026](/blog/site-propre-rapide-gratuit-2026/).

## Pourquoi pnpm existe ?

Parce que l’écosystème JavaScript adore empiler des dépendances.

Tu installes trois paquets, et tu te retrouves parfois avec :

- des centaines de sous-dépendances
- un `node_modules` énorme
- des installations lentes
- des duplications inutiles

`pnpm` a été pensé pour limiter ce bordel.

## Ce que pnpm change vraiment

Le gros truc de `pnpm`, c’est qu’il **évite de recopier bêtement les mêmes paquets partout**.

Au lieu de dupliquer les dépendances comme un bourrin dans chaque projet, il s’appuie sur un **store global** et relie ensuite les paquets au projet de manière intelligente.

Résultat :

- moins d’espace disque gaspillé
- installations souvent plus rapides
- structure plus stricte
- moins de comportements flous où “ça marche chez moi” juste parce qu’un paquet traînait quelque part

Dit autrement : `pnpm` essaie d’être **plus économe** et **moins permissif**.

## Pourquoi certains projets imposent pnpm

Parce que ce n’est pas juste une préférence esthétique.

Dans certains projets, utiliser `pnpm` permet :

- d’avoir un lockfile cohérent (`pnpm-lock.yaml`)
- de garder le même comportement pour toute l’équipe
- d’éviter des différences subtiles entre installations
- de mieux gérer les monorepos

Donc quand un projet impose `pnpm`, le message n’est pas juste :

> “on aime bien pnpm”

Le vrai message, c’est plutôt :

> “on veut éviter les écarts d’environnement et les bugs débiles.”

## La différence avec npm

Vu de loin, les commandes se ressemblent.

Par exemple :

```bash
npm install
pnpm install
```

ou :

```bash
npm add astro
pnpm add astro
```

Mais en dessous, ce n’est pas exactement la même logique.

### npm
- plus universel
- installé partout avec Node.js
- très pratique parce qu’il est déjà là
- mais parfois moins strict et moins efficace sur de gros projets

### pnpm
- plus économe
- souvent plus rapide
- meilleur pour garder un environnement propre
- demande juste d’accepter un outil en plus

## Le point qui surprend parfois

Avec `pnpm`, certains paquets mal fichus cassent plus vite.

Et ce n’est pas forcément un défaut de pnpm. C’est souvent parce que `pnpm` révèle des dépendances implicites ou des bricolages que `npm` laissait passer.

En gros, `pnpm` est moins tolérant envers le bazar.

Ça peut être un peu pénible au début, mais sur la durée, c’est souvent une bonne chose.

## Est-ce que pnpm remplace npm ?

Pas totalement.

En pratique :

- si tu fais un petit script vite fait, `npm` suffit largement
- si tu bosses sur un projet moderne, une équipe, un monorepo ou un setup un peu sérieux, `pnpm` devient souvent un meilleur choix

Donc non, `npm` n’est pas “mort”.
Mais `pnpm` est devenu une vraie option crédible, et pas juste un truc de puriste qui veut réinventer la roue.

## Pourquoi il devient populaire

Parce qu’il répond à un vrai problème.

Pas à un problème marketing. À un problème concret :

- trop de dépendances
- trop de duplication
- trop de lenteur
- trop de comportements pas nets

Quand un outil réduit ça sans tout casser, forcément il gagne du terrain.

## La version courte

Si je résume brutalement :

- **npm** est le standard historique
- **pnpm** fait le même boulot, mais de façon plus efficace et plus stricte
- il économise du disque
- il peut accélérer les installations
- il aide à garder des projets plus propres
- et s’il est imposé dans un repo, ce n’est généralement pas pour faire le malin

Bref : **pnpm, ce n’est pas juste un autre nom à apprendre. C’est une tentative assez saine de rendre l’écosystème Node un peu moins bordélique.**

Et si `npx` te paraît encore flou à côté, j’ai aussi un article simple sur [ce que fait `npx` exactement](/blog/npx-cest-quoi/) et un autre sur [ce qu’est un lockfile et pourquoi il compte vraiment](/blog/cest-quoi-un-lockfile/).
