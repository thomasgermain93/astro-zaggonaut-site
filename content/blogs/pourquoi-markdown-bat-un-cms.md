---
title: "Pourquoi Markdown bat souvent un CMS pour un site simple"
slug: "pourquoi-markdown-bat-un-cms"
description: "Pourquoi je préfère souvent des fichiers Markdown dans le repo plutôt qu’un CMS complet pour un site simple."
longDescription: "Dans cet article, j’explique pourquoi Markdown est souvent un meilleur choix qu’un CMS pour un blog, un site vitrine ou un portfolio simple : moins de complexité, moins de coûts, moins de maintenance."
tags: ["markdown", "cms", "strapi", "contenu", "blog", "site statique"]
readTime: 6
featured: true
timestamp: 2026-04-12
---

Dès qu’on parle de contenu sur un site, beaucoup de gens pensent immédiatement :

> il faut un CMS

En vrai, non.

Pour un blog simple, un portfolio, un site vitrine ou un petit site éditorial, un **fichier Markdown dans le repo** est souvent une solution plus saine qu’un CMS complet.

Pas parce que les CMS sont mauvais.
Parce qu’ils sont souvent **sur-dimensionnés** par rapport au besoin réel.

## Le réflexe CMS est souvent trop rapide

Un CMS apporte plein de choses utiles :

- une interface d’édition
- des rôles
- des workflows
- parfois une API
- une gestion centralisée du contenu

Tout ça est très bien… quand tu en as besoin.

Mais si ton besoin réel, c’est juste :

- publier quelques pages
- écrire quelques articles
- modifier du contenu de temps en temps
- garder une structure simple

alors un CMS peut surtout t’apporter :

- plus de maintenance
- plus de surface de panne
- plus de dépendances
- plus de friction

## Ce que Markdown fait très bien

Un fichier Markdown, c’est bête, mais c’est efficace.

Tu écris ton contenu dans un fichier, tu le versionnes avec le code, tu le pushes, et c’est réglé.

Tu gagnes immédiatement :

- zéro base de données
- zéro admin à sécuriser
- zéro serveur applicatif à maintenir
- zéro coût CMS
- zéro couche inutile entre ton contenu et ton site

Pour beaucoup de sites, c’est largement suffisant.

## Git devient ton back-office

C’est aussi ça qui est intéressant.

Quand ton contenu est dans le repo :

- GitHub sert d’historique
- les commits servent de trace
- les pull requests servent de revue
- le repo devient la source of truth

Ce n’est pas forcément idéal pour une équipe éditoriale de 15 personnes.
Mais pour un indépendant, une petite équipe, un portfolio ou un blog perso, c’est souvent largement plus propre.

## Le gros avantage : moins de moving parts

Chaque brique en moins, c’est :

- moins de bugs
- moins de mises à jour à gérer
- moins de failles potentielles
- moins de coûts cachés
- moins de dette technique

C’est exactement pour ça que je recommande souvent Markdown dans [ma stack simple pour lancer un site propre, rapide et gratuit en 2026](/blog/site-propre-rapide-gratuit-2026/).

Le web devient vite absurde quand on sort l’artillerie lourde pour publier trois pages et deux articles.

## Quand un CMS devient réellement utile

Soyons honnêtes : il y a des cas où un CMS est totalement logique.

Par exemple si tu as :

- plusieurs éditeurs non techniques
- un vrai back-office de contenu
- des permissions complexes
- des workflows de validation
- beaucoup de types de contenu
- des intégrations métier

Là, oui, un outil comme **Strapi** peut avoir du sens.

Mais si ton cas d’usage, c’est juste “j’ai besoin de publier du contenu proprement”, alors partir directement sur un CMS complet peut être une énorme perte de temps.

## Le faux argument du “professionnel”

Il y a aussi une idée bizarre qui traîne parfois :

> un vrai site pro doit avoir un CMS

Non.

Un site pro, c’est surtout un site :

- maintenable
- fiable
- rapide
- simple à faire évoluer

Si Markdown te donne ça avec moins de complexité, alors c’est une solution plus pro qu’un CMS monté par réflexe et jamais vraiment maîtrisé.

## Le lien avec les LLM

En 2026, c’est encore plus vrai.

Parce qu’avec un outil comme **Claude Code** ou **Cursor**, manipuler du contenu Markdown est très simple :

- créer des articles
- reformuler du texte
- proposer une structure
- ajouter des métadonnées
- relier des contenus entre eux

C’est beaucoup plus simple de travailler là-dessus que de faire discuter un LLM avec un back-office inutilement compliqué.

J’en parle justement dans mon article sur [là où Claude Code et Cursor aident vraiment, et là où ils racontent de la merde](/blog/claude-code-cursor-ou-ca-aide-vraiment/).

## La version courte

Si je résume brutalement :

- pour un site simple, **Markdown suffit souvent largement**
- ça réduit la complexité
- ça évite la base de données et la maintenance inutile
- ça s’intègre parfaitement avec GitHub
- ça marche très bien avec une stack statique moderne
- un CMS n’est utile que quand le besoin éditorial devient réellement plus complexe

Bref : **si ton site n’a pas besoin d’un vrai back-office, Markdown est souvent plus intelligent qu’un CMS.**

Et si tu veux élargir ça à l’hébergement et à la perf, lis aussi [pourquoi un site statique reste une excellente idée en 2026](/blog/pourquoi-un-site-statique-est-une-bonne-idee/).
