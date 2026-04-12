---
title: "Créer un site propre, rapide et gratuit en 2026 : la stack que je recommande"
slug: "site-propre-rapide-gratuit-2026"
description: "Ma stack simple pour créer un site propre, rapide et hébergé gratuitement en 2026 avec Claude Code ou Cursor."
longDescription: "Dans cet article, j’explique la stack que je recommande pour lancer un site moderne en 2026 : génération du projet avec Claude Code ou Cursor, contenu simple, GitHub comme source of truth, et hébergement gratuit via Cloudflare Pages ou GitHub Pages."
tags: ["next.js", "react", "cloudflare pages", "github", "markdown", "strapi", "cursor", "claude code"]
readTime: 6
featured: true
timestamp: 2026-04-12
---

Si je devais recommander aujourd’hui une manière simple de lancer un site **propre, rapide, maintenable et gratuit à héberger**, je ne partirais pas sur une usine à gaz.

Je prendrais une stack simple, efficace, et compatible avec les outils qu’on utilise déjà tous les jours.

En gros :

- un LLM pour générer la base du projet
- un framework frontend moderne
- du contenu simple
- GitHub comme source de vérité
- un hébergement statique propre derrière un CDN

Bref : **la stack du pauvre qui gagne**.

## 1. Le site : Claude Code ou Cursor pour générer la base

Aujourd’hui, partir d’une page blanche n’a plus beaucoup d’intérêt.

Tu peux très bien demander à **Claude Code** ou **Cursor** de te générer :

- la structure du projet
- les composants
- les pages
- le routing
- les sections principales
- une première direction visuelle

Tu décris ce que tu veux, tu fais générer une première base, puis tu itères.

Ce n’est pas magique. Il faut relire, corriger, simplifier et enlever les conneries éventuelles. Mais comme point de départ, c’est redoutablement efficace.

Pour ce type de projet, je recommande généralement :

- **React** si tu veux rester large et flexible
- **Next.js** si tu veux un cadre solide, connu, bien documenté

L’important, ce n’est pas de choisir l’outil “le plus hype”.
C’est de choisir un setup que tu peux encore comprendre et maintenir dans six mois.

## 2. Le contenu : Strapi si nécessaire, Markdown si tu veux rester léger

C’est souvent là que les gens se compliquent la vie trop tôt.

Si tu as vraiment besoin d’un back-office éditorial, de rôles, de workflows ou d’une équipe qui publie du contenu, **Strapi** peut être un bon choix comme headless CMS.

Mais franchement, pour beaucoup de sites vitrines, portfolios, blogs simples ou mini sites de contenu, tu peux faire bien plus simple :

- des fichiers **Markdown** dans le repo

Et là tu gagnes tout de suite :

- zéro base de données
- zéro coût d’infrastructure
- zéro maintenance serveur
- zéro panneau d’admin à sécuriser
- zéro emmerde inutile

Le contenu devient du versionné classique. Tu modifies un fichier, tu commit, tu pushes, c’est propre.

## 3. Le code : GitHub comme source of truth

Une fois le projet prêt, tu pushes sur **GitHub**.

GitHub fait trois choses très bien dans ce setup :

- c’est ton historique
- c’est ton versioning
- c’est le point de passage vers le déploiement

Et surtout, ça te force à garder un flux simple :

- tu modifies
- tu commits
- tu pushes
- ça déploie

Pas besoin de bricoler un serveur à la main pour un site qui pourrait très bien vivre comme un projet statique bien géré.

## 4. L’hébergement : Cloudflare Pages ou GitHub Pages

Pour l’hébergement, je recommande deux options simples.

### Cloudflare Pages

C’est souvent le meilleur choix si tu veux un truc propre, rapide et moderne.

Pourquoi :

- déploiement simple depuis GitHub
- CDN global inclus
- bon niveau de performance
- setup propre
- coût nul pour beaucoup de projets perso ou petits projets publics

Et surtout, l’expérience est assez fluide.

Si tu utilises un assistant de code pour générer la base du projet, j’ai aussi détaillé [où Claude Code et Cursor aident vraiment, et où ils commencent à raconter de la merde](/blog/claude-code-cursor-ou-ca-aide-vraiment/).

### GitHub Pages

C’est aussi une bonne option si tu veux aller au plus simple possible.

C’est un peu plus limité selon les cas, mais pour un site statique classique, ça fait largement le job.

## 5. Pourquoi cette stack marche bien en 2026

Parce qu’elle joue contre la complexité inutile.

Le piège classique, c’est de vouloir dès le départ :

- une base de données
- une API
- un back-office complet
- une infra compliquée
- un système qu’on n’aura ni le temps ni l’envie de maintenir

Alors que dans énormément de cas, ce qu’il faut vraiment, c’est :

- un site rapide
- un contenu simple à mettre à jour
- un hébergement fiable
- un coût proche de zéro
- un setup que tu peux faire évoluer ensuite

Cette stack coche tout ça.

## 6. Et les LLM dans tout ça ?

Le vrai intérêt de **Claude Code** ou **Cursor**, ce n’est pas juste de “coder à ta place”.

C’est de :

- poser une base vite
- explorer plusieurs variantes
- générer des composants répétitifs
- accélérer la mise en forme
- t’aider à refactorer
- débloquer les tâches chiantes

En revanche, il faut rester lucide :

- un LLM peut te sortir du code inutilement compliqué
- il peut te faire une belle démo fragile
- il peut introduire des choix techniques débiles si tu ne cadres pas bien la demande

Donc oui, c’est très puissant.
Mais seulement si tu gardes la main sur l’architecture, les choix et le niveau de complexité.

## 7. Le résultat concret

Avec cette approche, tu obtiens un site :

- **rapide**
- **propre**
- **facile à maintenir**
- **scalable pour pas mal de cas simples**
- **gratuit à héberger**
- **facile à faire évoluer avec un LLM**

Et surtout, tu restes dans une logique saine :

- peu de moving parts
- peu de coûts fixes
- peu de maintenance
- peu de dette inutile

## La version courte

Si je résume brutalement, ma reco en 2026 pour un site simple et sérieux, c’est :

- **Claude Code ou Cursor** pour générer la base
- **React / Next.js** pour le frontend
- **Markdown** dans le repo quand tu peux rester simple
- **Strapi** seulement si tu as un vrai besoin CMS
- **GitHub** comme source of truth
- **Cloudflare Pages** ou **GitHub Pages** pour l’hébergement

Si tu veux creuser certains morceaux de cette stack, j’ai aussi écrit sur [pourquoi Markdown bat souvent un CMS](/blog/pourquoi-markdown-bat-un-cms/), [pourquoi un site statique reste une excellente idée](/blog/pourquoi-un-site-statique-est-une-bonne-idee/) et [comment bien utiliser un LLM pour coder](/blog/comment-bien-utiliser-un-llm-pour-coder/).

Résultat :

**un site statique performant, maintenable, scalable dans beaucoup de cas, et qui peut coûter 0€/mois à héberger.**

Franchement, pour énormément de projets, ça suffit largement.
Et ça évite de monter une cathédrale technique pour publier trois pages et deux articles de blog.

Et si tu veux comprendre deux briques qu’on croise souvent dans ce genre de stack, tu peux aussi lire mes articles sur [npx](/blog/npx-cest-quoi/) et [pnpm](/blog/pnpm-cest-quoi/).
