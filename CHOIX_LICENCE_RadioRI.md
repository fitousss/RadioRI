# Choix de licence recommandé pour RadioRI

## Recommandation principale

**Choix recommandé : Business Source License 1.1 (BSL 1.1)**

### Pourquoi
Parce que ce choix permet de :

- laisser le code visible pour une démonstration à la DSI ;
- autoriser l'évaluation et les tests non productifs ;
- garder la maîtrise d'un déploiement en production ;
- conserver une vraie capacité de valorisation commerciale ;
- prévoir ensuite, si souhaité, une ouverture plus large du code à une date définie.

## Pourquoi je ne recommande pas MIT / Apache 2.0 ici

Ces licences autorisent très largement la réutilisation, y compris commerciale, avec peu de contraintes.
Elles sont excellentes pour maximiser l'adoption, mais pas pour garder un levier fort de valorisation.

## Pourquoi je ne recommande pas AGPL en premier choix

L'AGPL protège bien contre l'appropriation privée d'un service web, mais elle impose une logique de copyleft fort.
Pour une discussion avec une grande DSI hospitalière, ce n'est pas toujours le point d'entrée le plus simple si l'objectif est d'ouvrir une voie de contractualisation.

## Variante encore plus protectrice

Si la discussion avec l'AP-HP est encore très exploratoire :

- garder le dépôt **privé**, ou
- garder le dépôt **public sans licence open source**, donc en pratique **tous droits réservés**.

C'est plus protecteur juridiquement, mais moins lisible pour un partenaire technique et moins élégant pour une présentation produit.

## Paramétrage BSL conseillé

### Additional Use Grant suggéré

Usage gratuit autorisé uniquement pour :

- démonstration ;
- évaluation interne ;
- recette ;
- test non productif ;
- pilote limité non généralisé.

### Usages soumis à licence commerciale

- déploiement en production ;
- multi-sites ;
- revente ;
- intégration dans une offre tierce ;
- hébergement / exploitation par un prestataire ;
- adaptation pour un réseau hospitalier à grande échelle.

### Change Date

Je te conseille :

- soit **4 ans** après la première publication ;
- soit une date fixe si tu veux envoyer un signal d'ouverture future.

## Point critique avant toute licence

Le dépôt semble intégrer des contenus tiers ou inspirés de sources tierces.
Avant d'appliquer une licence au dépôt, il faut :

- isoler le **code que tu as écrit toi-même** ;
- retirer ou séparer les **contenus tiers** ;
- remplacer autant que possible les textes tiers par des liens vers les sources officielles ;
- ajouter un fichier `NOTICE`.

## Mention simple à mettre en haut du README

> Le code source original de RadioRI est distribué sous Business Source License 1.1.
> Les contenus tiers, documents externes, marques et textes non originaux restent soumis à leurs droits respectifs et sont exclus du champ de cette licence.

## Mon conseil pratique

Pour ton objectif précis — **présenter à la DSI de l'AP-HP tout en gardant une possibilité de valorisation** — je choisirais :

**BSL 1.1 + dépôt nettoyé des contenus tiers + README orienté démonstration hospitalière + NOTICE des contenus externes.**
