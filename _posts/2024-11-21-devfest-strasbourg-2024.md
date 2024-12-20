---
title: DevFest Strasbourg 2024
categories: [Conferences]
tags: []
---

Notes personnelles après le [DevFest Strasbourg 2024](https://devfest24.gdgstrasbourg.fr/).

## Idée pour réduire l'empreinte environnementale du numérique par 4
Tristant Nitot (ex Mozilla, W3C, comités numériques...)
- Loi de Moore (1965) : le nombre de transistors d'un microprocesseur double tous les deux ans
- Loi de Wirth (1995) : **les programmes ralentissent plus vite que le matériel n'accélère**
  - Poids page web x150 sur 25 ans, mémoire Office x170 sur 20 ans
  - Affichage plus rapide sur Apple II de 1983 que Lenovo X1
  - *"Ce qu'Intel donne, Microsoft le reprend"*
- **50 ans lucratifs pour l'industrie**
  - Ajout effréné de fonctionnalités peu performantes grâce à nouvelle puissance
  - 80% smartphones "ralentis" pourtant fonctionnels jetés après 3 ans !
- **Système non tenable à cause du changement climatique**
  - +3°C selon GIEC en 2100 (+4 en France) malgré "efforts" actuels
  - +1,5°C visé par accord de Paris que si réduction drastique
- **Loi d'erooM** (effort radicalement organisé d'optimisation en masse, Tristant Nitot) : **optimiser d'un facteur 2 tous les 2 ans** => plus besoin de nouveau matériel
- Méthodo développeur : **maintenabilité vs perf**
  - **Junior : se former (craft)** pour arriver à maintenable mais peu performant
  - **Sénior : optimiser (erooM)** pour arriver au meilleur compromis maintenabilité/perf

## Le produit entre la qualité et l’over-engineering
Jihène Mejri (Bforbank)
- Expérience courante : qualité visée mais surcomplexité/perfs dégradées au final
- Qualité parfois mesurée avec indicateurs "pastèques" (vert extérieur, rouge intérieur)
- Triangle QCD classique : qualité vs rapidité vs coût
- DORA (DevOps Research & Assessment) plus récent : **fiabilité (qualité) vs rendement (rapidité)**
- **4 métriques DORA** (+ 24 capabilities dans livre Accelerate)
  - **DF (deployment frequency)** = fréquence de déploiements sur une période => rendement
  - **MLTC (mean lead time to change)** = temps moyen entre décision et déploiement d'un sujet => rendement
  - **MTTR (mean time to recovery)** = temps moyen entre découverte problème prod et résolution => fiabilité
  - **CFR (changement failure rate)** = nombre d'incidents/nombre de déploiements => fiabilité
- Comment éviter l'over-engineering
  - Eviter "bonnes pratiques" aveugles, notamment [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) technique
  *"Duplication is far cheaper than the wrong abstraction"*, Sandi Metz
  - **Ne pas être dogmatique, s'adapter au contexte, rester simple** ([YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it), [KISS](https://en.wikipedia.org/wiki/KISS_principle))
  - Se méfier du code générique

## Craft, TDD, DDD... Faut-il culpabiliser de ne pas en faire ?
Matthieu Lempereur (freelance PHP)
- LinkedIn auj : *"les bons développeurs font du (TDD, BDD, trunk based development, pair/mob programming, no estimate...)"*
- Mais contraintes réelles : organisation entreprise, culture technique et compétences équipe
- **"Bonnes pratiques" = puits sans fond**
- Pratiques = choix d'équipe (chacun a son opinion !)
- **Expérimenter et trouver ce qui fonctionne pour son équipe**
- **Même objectif au fond : développer une app optimale pour ses utilisateurs**

## Le monde a besoin de hackers
Mathis Hammel (formateur IA/cybersécurité)
- **Hack = curiosité, créativité, partage** (sans connotation négative)
- Dernier projet : jouer à doom sur croix de pharmacie (partage youtube)
- Ca sert à quoi ? Hobby fun mais retombées réelles
  - Jobs et Wozniak vendent des boîtiers pour hacker le téléphone pendant 3 ans avant de créer Apple
  - Mathis joue avec la lib random python avant d'améliorer ses perfs
  - Mathis développe un catalogue des fausses photos de profil qui permet de démanteler des réseaux d'ingérence sur X et LinkedIn
  - Marcus Hutchins achète un domaine étrange en dur dans le ransomware WannaCry ce qui le désactive
- **Petits projets persos pour apprendre vite**
- Chance dans la tech : **explorer, réinventer, partager**

## Fondamentaux du développement web
Bertrand Delacrétaz (Adobe, ex board Apache)
- Web d'apparence simple : client (HTML, CSS, JS) communique avec serveur via HTTP
- Mais nombreux fondamentaux requis pour site web grand public solide
- Plateforme Web : **utiliser HTML, CSS et JS modernes** ([doc MDN](https://developer.mozilla.org/fr/), compatibilité caniuse.com)
- Apparence : HTML sémantique, reste avec CSS, responsive (80% trafic mobile)
- Ne pas oublier **UX**, i18n et a11y
- Images : optimiser formats de l'ordi fibré au smartphone en mouvement
- Vidéos : proposer streaming adaptatif pour lecture immédiate
- **Sécurité** : utiliser CORS et HTTPS, se protéger des XSS, CSRF, DDoS...
- Performance : lent = pas sérieux voire perte commerciale => **optimiser Core Web Vitals**
  - Utiliser caches navigateur et HTTP, CDN
  - **Lean & mean : supprimer l'inutile, viser la simplicité**
  - **HTML first, CSS next, JS minimal**
  - Pas de framework JS si temps de visite très court

## Bruno, le Postman killer ?
Alan Duchene (freelance)
- Postman = outil dév API très complet dans le cloud (leader)
- Bruno = client d'API simple, open source et hors ligne (startup)
- **Avantages Bruno**
  - **Hors ligne** => sécurisé et performant
  - Tout est fichier => **partage via git**
  - Module de tests dans version payante ?
- Mais Alan n'a pas encore d'XP en prod
 
## 10 fonctionnalités utiles du web que vous ne connaissez pas
Olivier Leplus (AWS)
- Baseline = initiative Google pour pousser les navigateurs à implémenter les nouveautés HTML, CSS et JS
- Quelques nouveautés citées
  - JS temporal API : module de **date plus fiable** et complet
  - JS array : utils fonctionnels, for await...
  - JS promises : utils
  - JS compression stream : **zip dans navigateur** !
  - CSS @property : typage propriété
  - CSS relative color : hsl(from otherColor ...
  - CSS vertical align : **{ align-content: center }**
  - CSS columns : .container{columns: 250px;} img{width: 100%;} => colonnes img responsive
  - CSS attr() : accès dynamique attribut HTML !
  - JS private prop : # pour marquer prop privé
  - JS ??= : valorisé si nul (comme C#)
  - JS Error cause : propagation erreur
  - Node test : module de test natif dans nodeJs