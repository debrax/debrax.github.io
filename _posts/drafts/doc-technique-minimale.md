---
layout: post
title: "Doc technique minimale ?"
date: 2021-03-04 20:29:33 +0100
categories: programming
---

Arriver dans un projet existant n'est jamais facile. Du métier obscur, des dépendances farfelues et une infrastructure maison, il est rarement possible de se lancer de manière autonome...

Et si on se facilitait la vie ? Ma proposition : maintenir systématiquement une **doc technique sous la forme d'un README inclus dans les sources**. Son but : rassembler les infos minimales pour compiler, lancer localement, livrer et déboguer le projet.

## Modèle proposé

```
# Nom du projet

## GOAL
// Courte description métier du projet

## BUILD
// Tutoriel pour compiler le projet

## RUN
// Tutoriel pour lancer le projet localement

## DEPLOY
// Tutoriel pour livrer le projet dans les différents environnements

## DEBUG
// Infos pour déboguer le projet dans les différents environnements
```

## FAQ

Pourquoi dans les sources ? Plus la doc s'en éloigne, plus elle a de chance d'être oubliée donc obsolète.

Pourquoi du markdown ? Le format est intuitif et pris en charge nativement par l'interface Github & Cie.

Pourquoi du métier dans une doc technique ? Comprendre la finalité du projet est vital pour être efficace dans sa maintenance.

Pourquoi perdre du temps pour une doc ? La mise à jour est simplissime et le temps gagné à l'arrivée du prochain dév en vaut la chandelle : toujours ça de moins quand il viendra vous voir ([RTFM](https://en.wikipedia.org/wiki/RTFM)) !

## Dans la vraie vie

J'ai commencé à appliquer ce modèle sur différents projets et les retours sont plutôt positifs. Il est encore trop tôt pour évaluer l'impact de cette doc minimale mais je suis convaincu qu'elle peut jouer un rôle certain dans la maintenabilité d'un projet !

Et vous, qu'en pensez-vous ? Des idées d'amélioration du modèle ? Des retours d'expérience sur les docs techniques que vous avez croisées ? :)