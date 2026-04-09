---
title: "npx, ça sert à quoi exactement ?"
slug: "npx-cest-quoi"
description: "Explication simple de npx : à quoi ça sert, quand l’utiliser, et pourquoi ce n’est pas juste un autre npm."
longDescription: "Dans cet article, j’explique ce que fait npx, pourquoi il est pratique pour lancer un outil sans l’installer globalement, et dans quels cas il vaut mieux l’utiliser — ou l’éviter."
tags: ["npx", "npm", "node.js", "cli", "javascript"]
readTime: 5
featured: true
timestamp: 2026-04-09
---

Quand on touche à l’écosystème Node.js, on voit souvent passer des commandes du genre :

```bash
npx create-next-app
```

ou

```bash
npx astro add tailwind
```

Si tu débutes, ça peut être un peu flou. On pourrait se dire : **pourquoi `npx` ? Pourquoi pas juste `npm` ?**

La réponse courte : **`npx` sert à exécuter un outil Node.js sans devoir l’installer globalement à la main.**

## La différence simple entre npm et npx

- **`npm`** sert surtout à **installer** et **gérer** des paquets
- **`npx`** sert à **exécuter** un paquet, en particulier un CLI

Exemple :

```bash
npm install -g create-next-app
```

ça installe l’outil globalement sur ta machine.

Alors que :

```bash
npx create-next-app
```

lance directement l’outil sans te forcer à le garder installé globalement.

## Pourquoi c’est pratique ?

Parce que ça évite de transformer ta machine en décharge à CLI.

Si tu installes tout en global :

- tu accumules des outils que tu n’utilises qu’une fois
- tu peux te retrouver avec de vieilles versions qui traînent
- tu perds vite en lisibilité sur ce qui est réellement nécessaire à ton projet

Avec `npx`, tu peux lancer un outil ponctuel, faire le job, puis passer à autre chose.

C’est particulièrement utile pour :

- créer un nouveau projet
- lancer un générateur de code
- utiliser un utilitaire occasionnel
- tester rapidement un CLI

## Ce que fait vraiment npx

En pratique, `npx` va chercher le binaire à exécuter :

1. d’abord dans les dépendances locales du projet si l’outil y est déjà installé
2. sinon, il peut le récupérer à la volée depuis le registre npm
3. puis il l’exécute

Ça veut dire qu’une commande comme :

```bash
npx eslint .
```

peut utiliser l’instance locale de `eslint` du projet, ce qui est en général une bonne chose.

Pourquoi ? Parce que toute l’équipe utilise alors la **même version** de l’outil, au lieu de dépendre d’un truc global installé différemment sur chaque machine.

## Le cas le plus courant : lancer un starter

Le cas d’usage classique, c’est le bootstrap d’un projet.

Exemples :

```bash
npx create-next-app@latest
npx create-vite@latest
npx astro@latest
```

L’idée est simple :

- tu veux exécuter l’outil maintenant
- tu n’en as peut-être rien à foutre après
- donc inutile de l’installer globalement

C’est propre, rapide et ça limite le bordel.

## Quand il vaut mieux éviter `npx`

`npx` est pratique, mais ce n’est pas magique.

Il y a des cas où ce n’est pas le meilleur choix.

### 1. Pour un outil utilisé tout le temps dans un projet

Si un outil fait partie du projet, mieux vaut souvent l’installer en dépendance locale.

Exemple :

```bash
npm install -D eslint
```

puis :

```bash
npx eslint .
```

Là, `npx` sert juste de lanceur pour un outil **déjà présent dans le projet**. C’est très bien.

### 2. Pour un outil sensible ou inconnu

Lancer à la volée un paquet trouvé sur npm, ce n’est pas un geste anodin.

Si tu fais :

```bash
npx un-truc-random-trouvé-sur-internet
```

tu es littéralement en train d’exécuter du code tiers sur ta machine.

Donc règle simple :

- si c’est un outil connu et standard, pas de souci particulier
- si c’est un paquet obscur avec 12 téléchargements, réfléchis deux secondes avant de lui ouvrir la porte

## `npx` ne remplace pas `npm`

C’est un point important.

`npx` n’est pas une version “plus moderne” de `npm`. Ce n’est pas non plus un concurrent.

Les deux n’ont juste pas le même rôle :

- `npm` gère les paquets
- `npx` exécute des commandes liées à ces paquets

Tu peux voir `npx` comme un **raccourci pratique pour lancer un binaire Node sans t’embarrasser d’une installation globale**.

## Le piège classique

Beaucoup de gens confondent :

```bash
npm astro
```

et

```bash
npx astro
```

La première n’a pas de sens dans ce contexte.
La deuxième oui, parce qu’on demande à exécuter le CLI `astro`.

C’est pour ça que `npx` revient souvent dans les docs d’installation rapide.

## La version courte

Si je résume brutalement :

- **`npm` installe**
- **`npx` exécute**
- `npx` est très utile pour les commandes ponctuelles et les starters
- c’est aussi pratique pour lancer les outils locaux d’un projet
- mais il ne faut pas exécuter n’importe quel paquet au hasard comme un bourrin

Bref : **`npx`, c’est le moyen propre de lancer un outil Node sans pourrir ton système avec des installations globales inutiles.**
