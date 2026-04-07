---
title: "i18n, ça veut dire quoi exactement ?"
slug: "i18n-cest-quoi"
description: "Explication simple de i18n, l10n et de la différence entre préparer un produit pour plusieurs langues et le traduire réellement."
longDescription: "i18n veut dire internationalization. Dans cet article, j’explique d’où vient cette abréviation, à quoi elle sert concrètement dans un site ou une app, et pourquoi il faut la distinguer de l10n, la localisation."
tags: ["i18n", "l10n", "localisation", "web", "produit"]
readTime: 4
featured: true
timestamp: 2026-04-07
---

Quand on bosse dans le web, on tombe vite sur des abréviations un peu obscures. **i18n** en fait partie. Vu de loin, ça ressemble à un mot de passe cassé. En vrai, c’est juste une manière courte d’écrire **internationalization**.

## Pourquoi « i18n » ?

Le principe est simple :

- la première lettre est **i**
- la dernière lettre est **n**
- et **18** représente le nombre de lettres entre les deux

**internationalization** → **i18n**

Même logique pour d’autres raccourcis connus :

- **l10n** = localization
- **a11y** = accessibility

Ce n’est pas élégant, mais c’est pratique quand on en parle souvent.

## i18n, concrètement, ça veut dire quoi ?

L’**internationalisation**, c’est le fait de **préparer un site, une app ou un produit pour pouvoir fonctionner dans plusieurs langues, pays ou contextes culturels**.

Autrement dit : on construit le système de façon à ce qu’il puisse gérer plusieurs variantes sans devoir tout recoder plus tard.

Par exemple, un produit pensé pour le i18n évite de hardcoder partout :

- les textes dans les composants
- le format des dates
- le format des nombres
- la devise
- certains choix d’interface dépendants de la langue

Donc au lieu d’écrire directement un bouton avec `Commander maintenant`, on prévoit une couche de traduction ou de configuration.

## La différence entre i18n et l10n

C’est là que les gens mélangent souvent tout.

### i18n = préparer la structure
Tu rends le produit capable de gérer plusieurs langues et contextes.

### l10n = adapter à une langue ou un marché précis
Tu fais la traduction et les adaptations concrètes.

Exemple simple :

- **i18n** : ton app sait afficher du français, de l’anglais, gérer différents formats de date et charger les bons textes selon la locale
- **l10n** : tu ajoutes réellement la version française, anglaise ou néerlandaise avec les bons mots, les bons formats et parfois les bons visuels

Donc :

- **i18n = architecture**
- **l10n = adaptation réelle**

## Pourquoi c’est important ?

Parce que si tu ne penses pas au i18n assez tôt, ça devient vite pénible.

Tu te retrouves avec :

- des textes codés en dur partout
- des layouts qui cassent quand une traduction est plus longue
- des formats de date absurdes pour certains pays
- des URLs ou slugs impossibles à faire évoluer proprement

À l’inverse, si c’est prévu dès le départ, ajouter une nouvelle langue devient surtout un sujet de contenu et de QA, pas une opération chirurgicale dans tout le codebase.

## Ce que le i18n ne veut pas dire

Faire du i18n ne veut **pas** dire que ton produit est déjà multilingue.

Tu peux avoir une app bien pensée pour l’internationalisation sans avoir encore traduit quoi que ce soit. Elle est juste prête.

De la même façon, traduire quelques chaînes à la main ne veut pas dire que ton produit est correctement internationalisé.

Si l’architecture est mauvaise, tu peux avoir une pseudo version anglaise qui fonctionne à moitié, avec des morceaux qui débordent de partout.

## Exemples très concrets

Sur un site web, i18n peut couvrir :

- des fichiers de traduction
- une détection de langue
- des routes du type `/fr`, `/en`, `/nl`
- des formats de date différents selon la langue
- des libellés qui changent proprement sans toucher au composant

Sur un e-commerce, ça peut aussi inclure :

- la devise
- les taxes
- les modes d’expédition
- certaines formulations légales

Et là on voit vite que ce n’est pas juste une question de traduction. C’est un vrai sujet produit.

## La version courte

Si je devais le résumer brutalement :

- **i18n** = tu prépares ton produit pour plusieurs langues/pays
- **l10n** = tu l’adaptes réellement à une langue/pays donné

Donc quand quelqu’un te dit _« il faut gérer le i18n »_, il ne parle pas juste de traduire trois boutons. Il parle de faire les choses proprement pour éviter un futur bordel.
