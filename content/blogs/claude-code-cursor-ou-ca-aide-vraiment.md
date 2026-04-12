---
title: "Claude Code / Cursor : là où ça aide vraiment, et là où ça raconte de la merde"
slug: "claude-code-cursor-ou-ca-aide-vraiment"
description: "Ce que Claude Code et Cursor font vraiment bien, et les cas où ils donnent surtout une illusion de vitesse."
longDescription: "Dans cet article, j’explique où Claude Code et Cursor apportent un vrai gain de temps, où ils peuvent faire perdre du temps, et comment les utiliser intelligemment sans leur confier toute l’architecture du projet."
tags: ["claude code", "cursor", "llm", "développement", "javascript", "productivité"]
readTime: 7
featured: true
timestamp: 2026-04-12
---

On voit beaucoup de discours un peu trop enthousiastes sur **Claude Code**, **Cursor** et les assistants de dev en général.

D’un côté, tu as les gens qui te vendent ça comme si l’ingénierie logicielle était terminée.
De l’autre, tu as ceux qui disent que ça ne sert à rien.

Comme souvent, la vérité est au milieu.

Oui, ces outils peuvent faire gagner un temps énorme.
Mais non, ils ne remplacent pas un cerveau, une architecture propre, ni un minimum de jugement technique.

Si tu veux les utiliser intelligemment, il faut savoir **où ça aide vraiment** et **où ça commence à raconter de la merde avec beaucoup d’assurance**.

## Là où ça aide vraiment

Il y a des cas où le gain est très concret.

### 1. Générer une base de projet

Pour démarrer un projet, c’est souvent excellent.

Tu peux demander :

- une structure de pages
- une arborescence cohérente
- des composants de base
- un layout
- une navigation
- une première direction UI

Ce n’est pas forcément le code final, mais ça te fait gagner le temps le plus chiant : celui du démarrage.

C’est exactement pour ça que je recommande ce genre d’outil dans [ma stack simple pour créer un site propre, rapide et gratuit en 2026](/blog/site-propre-rapide-gratuit-2026/).

### 2. Produire du code répétitif

Dès qu’il y a des tâches un peu mécaniques, ça peut être très rentable.

Par exemple :

- décliner plusieurs composants proches
- générer des variantes de formulaire
- écrire des types
- ajouter des pages sur une même structure
- refactorer une série de blocs similaires

Ce n’est pas le travail le plus noble du monde, donc autant le déléguer quand c’est cadré.

### 3. Refactorer avec un objectif clair

Si tu sais déjà ce que tu veux obtenir, Claude Code ou Cursor peuvent vraiment aider.

Exemples :

- découper un composant trop gros
- renommer proprement certaines structures
- factoriser des morceaux répétitifs
- migrer une API ancienne vers une nouvelle approche

La condition, c’est que la demande soit précise.

Plus ton objectif est clair, plus l’outil devient utile.

### 4. Explorer rapidement plusieurs options

Tu hésites entre deux structures ? Deux approches de composant ? Deux manières d’organiser un écran ?

Là, ces outils sont très bons pour générer rapidement des variantes.

Pas pour décider à ta place. Mais pour te donner de la matière à comparer.

### 5. Débloquer une tâche pénible

Il y a aussi toutes les situations où tu sais globalement ce que tu veux faire, mais tu n’as pas envie de passer 40 minutes à recâbler un détail chiant.

Là encore, très utile.

## Là où ça raconte de la merde

C’est là qu’il faut être un peu moins naïf.

### 1. Quand tu lui laisses définir l’architecture tout seul

Très mauvaise idée.

Si tu laisses un LLM choisir librement :

- la structure globale
- les patterns
- les conventions
- les dépendances
- le découpage technique

il peut te sortir un truc qui a l’air propre pendant dix minutes, puis devient pénible à maintenir dès que le projet grossit.

Il est bon pour proposer.
Pas pour gouverner à ta place.

### 2. Quand le projet devient un peu subtil

Dès qu’on sort du CRUD ou du composant standard, ça se complique.

Par exemple :

- logique métier sensible
- auth un peu sérieuse
- performance fine
- concurrence
- edge cases
- migrations délicates
- infra réelle

Là, il peut aider localement, mais il commence aussi à inventer, simplifier à tort, ou te vendre des solutions fragiles avec un aplomb impressionnant.

### 3. Quand tu confonds vitesse de génération et vitesse de livraison

C’est un piège classique.

Oui, il peut te sortir 800 lignes vite.
Mais si derrière tu dois :

- relire
- corriger
- simplifier
- débugger
- enlever la moitié

alors tu n’as pas forcément gagné du temps.

Tu as juste déplacé le boulot.

### 4. Quand tu lui demandes de “faire propre” sans contrainte

“Fais-moi ça bien.”
“Refactore ça proprement.”
“Améliore l’architecture.”

Ce genre de prompt flou produit souvent du code plus abstrait, plus verbeux, plus intelligent en apparence… et parfois plus chiant en réalité.

Un LLM adore sur-concevoir si tu lui laisses la place.

### 5. Quand tu le prends pour une source de vérité

Ça, c’est non.

Un assistant de code peut :

- oublier une contrainte
- halluciner une API
- inventer une option de config
- écrire du code plausible mais faux
- casser discrètement une logique existante

Donc si tu ne vérifies pas, tu signes toi-même le chèque de la future merde.

## Là où ils sont les plus utiles en vrai

À mon avis, le meilleur usage de Claude Code ou Cursor, c’est :

- **accélérer l’exécution**
- **pas externaliser le jugement**

En gros :

- toi, tu gardes la direction
- l’outil, tu lui fais produire, explorer, reformuler, accélérer

C’est là que le ratio gain / emmerdes devient intéressant.

Si tu veux la version plus opérationnelle, j’ai aussi écrit un article sur [comment bien utiliser un LLM pour coder sans transformer ton repo en chantier](/blog/comment-bien-utiliser-un-llm-pour-coder/).

## Une bonne règle simple

Si la tâche est :

- répétitive
- bien cadrée
- testable
- locale
- réversible

alors un LLM a de bonnes chances d’être utile.

Si la tâche est :

- floue
- systémique
- structurante
- difficile à valider
- pleine de cas limites

alors il faut ralentir et reprendre la main.

## Le lien avec le reste de la stack

C’est aussi pour ça que je recommande souvent des stacks simples.

Moins ton projet est inutilement compliqué, plus un assistant de code peut réellement aider sans transformer ton repo en chantier douteux.

Par exemple, si tu pars sur un site simple avec contenu en Markdown, GitHub comme source of truth, et déploiement propre, tu réduis déjà beaucoup la surface de merde potentielle.

Et si tu manipules souvent l’écosystème Node autour de ça, tu peux aussi jeter un œil à mes articles sur [npx](/blog/npx-cest-quoi/), [pnpm](/blog/pnpm-cest-quoi/) et [les lockfiles](/blog/cest-quoi-un-lockfile/), parce que ce sont justement des trucs qu’on croise vite dans ce genre de setup.

## La version courte

Si je résume brutalement :

### Claude Code / Cursor aident vraiment pour :
- démarrer un projet
- générer du code répétitif
- refactorer avec un objectif clair
- explorer des variantes
- débloquer des tâches chiantes

### Claude Code / Cursor racontent souvent de la merde quand :
- tu leur laisses définir l’architecture
- le sujet devient subtil
- tu confonds vitesse d’écriture et vitesse de livraison
- tu donnes des consignes trop floues
- tu oublies de vérifier

Bref : **ce sont d’excellents multiplicateurs de vitesse, mais de très mauvais remplaçants du jugement technique.**
