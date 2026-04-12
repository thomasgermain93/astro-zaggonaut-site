---
title: "Comment bien utiliser un LLM pour coder sans transformer ton repo en chantier"
slug: "comment-bien-utiliser-un-llm-pour-coder"
description: "Quelques règles simples pour utiliser Claude Code ou Cursor intelligemment sans perdre le contrôle technique du projet."
longDescription: "Dans cet article, je résume une manière saine d’utiliser un LLM pour coder : cadrer les demandes, garder la main sur l’architecture, vérifier les sorties et éviter la sur-complexité."
tags: ["llm", "claude code", "cursor", "développement", "productivité", "architecture"]
readTime: 6
featured: false
timestamp: 2026-04-12
---

Les assistants de code peuvent faire gagner énormément de temps.

Ils peuvent aussi transformer un repo propre en chantier douteux si tu les utilises n’importe comment.

Le problème, ce n’est pas seulement le modèle.
C’est aussi la manière dont tu t’en sers.

Voici une version simple de ce qui marche bien chez moi.

## 1. Donne un cadre clair

Plus la demande est floue, plus la sortie risque d’être bancale.

Un prompt du style :

> améliore ça

est une invitation à la sur-ingénierie.

Alors qu’un prompt comme :

> découpe ce composant en 3 sous-composants sans changer le comportement, garde Tailwind, évite d’ajouter de dépendances

est beaucoup plus utile.

Le LLM travaille mieux quand :

- l’objectif est clair
- les contraintes sont claires
- le périmètre est clair

## 2. Garde la main sur l’architecture

C’est probablement la règle la plus importante.

Le LLM peut t’aider à exécuter.
Mais il ne devrait pas décider seul :

- de la structure globale du projet
- des conventions
- des dépendances
- des abstractions principales

Sinon tu risques de te retrouver avec un codebase qui a l’air intelligent… mais que personne n’a vraiment pensé.

J’en parle plus frontalement dans [mon article sur là où Claude Code et Cursor aident vraiment, et là où ils racontent de la merde](/blog/claude-code-cursor-ou-ca-aide-vraiment/).

## 3. Utilise-le surtout sur des tâches locales et testables

Les meilleurs cas d’usage, c’est souvent quand la tâche est :

- locale
- précise
- réversible
- facile à vérifier

Par exemple :

- écrire un composant
- refactorer un bloc précis
- générer un schéma répétitif
- corriger une erreur ciblée
- aider à écrire des tests

Plus la tâche est large et floue, plus le risque grimpe.

## 4. Vérifie toujours les sorties

Toujours.

Même quand la réponse a l’air propre.
Même quand le code compile.
Même quand le diff semble raisonnable.

Pourquoi ?
Parce que le LLM peut très bien :

- casser un edge case
- halluciner une API
- oublier une contrainte existante
- ajouter de la complexité cachée
- introduire une dette technique sournoise

Donc oui, il faut relire.
C’est non négociable.

## 5. Refuse la complexité gratuite

Beaucoup de sorties de LLM ont un problème simple :

elles sont souvent **plus compliquées que nécessaire**.

Tu demandes une amélioration, et tu récupères :

- une abstraction de plus
- deux helpers inutiles
- un pattern “propre” mais lourd
- une couche supplémentaire qui n’apporte pas grand-chose

Il faut apprendre à couper sans pitié.

## 6. Préfère itérer en petites étapes

Au lieu de demander :

> refais-moi toute l’application

il vaut mieux avancer par morceaux :

- étape 1 : structure
- étape 2 : composant X
- étape 3 : refacto ciblée
- étape 4 : nettoyage

Tu gardes plus de contrôle, et tu vois plus vite quand ça commence à partir en vrille.

## 7. Utilise une stack simple autour

Plus ton projet est simple, plus un LLM peut réellement t’aider sans faire exploser la complexité.

C’est aussi pour ça que je recommande souvent :

- une stack frontend claire
- du contenu simple
- un repo Git propre
- un hébergement statique quand c’est possible

J’ai détaillé ça dans [ma stack recommandée pour lancer un site en 2026](/blog/site-propre-rapide-gratuit-2026/).

## La version courte

Si je résume brutalement :

- donne un cadre clair
- garde la main sur l’architecture
- utilise le LLM sur des tâches locales et testables
- relis toujours les sorties
- coupe la complexité gratuite
- avance par petites étapes

Bref : **un LLM est un bon accélérateur, pas un bon pilote automatique.**

Et si tu veux la version un peu plus critique sur les limites concrètes de ces outils, lis aussi [là où Claude Code et Cursor aident vraiment, et là où ils racontent de la merde](/blog/claude-code-cursor-ou-ca-aide-vraiment/).
