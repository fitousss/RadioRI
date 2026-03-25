# RadioRI

**RadioRI** est une application de coordination pour la **radiologie interventionnelle**.
Elle vise à structurer le parcours d’une demande de geste, depuis la **prescription** jusqu’à la **validation**, la **programmation** et le **suivi organisationnel**.

Le projet est aujourd’hui présenté comme un **prototype fonctionnel** orienté métier, pensé pour un environnement hospitalier de type **AP-HP**.

---

## Objectif

Dans beaucoup d’établissements, les demandes de radiologie interventionnelle circulent encore par téléphone, email, fax, DPI partiellement structuré ou échanges informels.

Cela entraîne souvent :

- des demandes incomplètes ;
- des délais de réponse variables ;
- une perte de traçabilité ;
- des difficultés de priorisation ;
- une programmation hétérogène des gestes ;
- une dépendance à la mémoire des équipes pour les protocoles et prérequis.

**RadioRI** a pour but de proposer un point d’entrée unique, simple et structuré pour :

- déposer une demande de geste ;
- demander un avis de faisabilité ;
- centraliser les informations cliniques utiles ;
- standardiser la validation médicale ;
- fluidifier la programmation ;
- diffuser les protocoles péri-procéduraux ;
- améliorer la visibilité opérationnelle de l’activité.

---

## Utilisateurs cibles

L’application est pensée pour quatre profils principaux :

### 1. Prescripteurs
- création d’une demande de geste ;
- demande d’avis RI ;
- dépôt de documents ;
- lecture des réponses, validations, refus ou demandes de consultation.

### 2. Radiologues interventionnels
- analyse et tri des demandes ;
- validation, refus ou demande de consultation pré-geste ;
- réponse aux avis RI ;
- ajout de commentaires médicaux et organisationnels.

### 3. Secrétariat / coordination
- programmation des gestes validés ;
- affectation de la date, de la salle, du radiologue, de l’anesthésie et des consignes.

### 4. Administration métier
- gestion du catalogue des gestes ;
- gestion des salles ;
- configuration métier minimale.

---

## Fonctionnalités principales

### Gestion des demandes de gestes
- formulaire structuré de demande ;
- identification du patient ;
- indication clinique ;
- niveau d’urgence ;
- anticoagulants / antiagrégants ;
- disponibilité du bilan ;
- pièces jointes ;
- suivi du statut de la demande.

### Gestion des avis RI
- envoi d’une question ciblée à l’équipe de RI ;
- réponse de faisabilité ;
- proposition de conditions de réalisation ;
- recommandation de délai ;
- retour écrit traçable.

### Validation médicale
- validation ;
- refus motivé ;
- demande de consultation pré-geste ;
- commentaire médical visible selon le rôle.

### Programmation
- liste des gestes validés à programmer ;
- affectation d’une date et heure ;
- choix de la salle ;
- choix du radiologue opérateur ;
- saisie de notes de préparation ;
- vue planning des gestes programmés.

### Protocoles et aide organisationnelle
- consultation de protocoles péri-procéduraux relatifs aux fluidifiants ;
- affichage du niveau de risque du geste ;
- mise à disposition de fiches d’information patient.

### Pilotage d’activité
- statistiques d’activité ;
- volumes de demandes ;
- volumes d’avis ;
- indicateurs de validation, refus et programmation.

### Administration métier
- ajout, modification, désactivation de gestes ;
- gestion des salles de RI ;
- adaptation du paramétrage à l’organisation locale.

---

## Positionnement pour la DSI

RadioRI n’a pas vocation à remplacer seul l’ensemble du SIH.

Le bon positionnement est celui d’un **outil métier de coordination**, pouvant s’intégrer à terme avec :

- l’authentification institutionnelle ;
- le DPI / dossier patient ;
- la gestion des rendez-vous ;
- la messagerie interne ;
- l’archivage documentaire ;
- éventuellement les standards d’échange (HL7 / FHIR selon la stratégie locale).

L’intérêt pour la DSI est double :

1. **Standardiser un circuit métier aujourd’hui souvent diffus**
2. **Préparer une intégration progressive dans un cadre urbanisé et sécurisé**

---

## Valeur métier attendue

- réduction des demandes incomplètes ;
- meilleure priorisation des urgences ;
- diminution des appels et relances non tracés ;
- homogénéisation des pratiques de validation ;
- amélioration de la lisibilité du planning ;
- meilleure continuité entre prescripteurs, RI et secrétariat ;
- accès rapide à une information procédurale structurée.

---

## État actuel du projet

Le dépôt actuel correspond à un **prototype front-end** permettant de démontrer l’expérience utilisateur et la logique métier.

### Ce que montre déjà le prototype
- une interface exploitable ;
- une logique de rôles ;
- des écrans métier cohérents ;
- un parcours demande → validation → programmation ;
- un premier niveau de sécurisation d’interface ;
- une démonstration de valeur fonctionnelle.

### Ce qui reste à industrialiser
- backend sécurisé ;
- base de données ;
- authentification institutionnelle / SSO ;
- gestion fine des habilitations ;
- journal d’audit complet ;
- hébergement interne ou HDS adapté ;
- traçabilité réglementaire ;
- interopérabilité SIH ;
- supervision et maintenance ;
- tests, recette, CI/CD, documentation d’exploitation.

---

## Sécurité et conformité

Le prototype intègre déjà une logique de sécurité d’interface, mais il doit être considéré comme une **base de démonstration** et non comme une version de production.

Pour une version établissement, les points suivants devront être cadrés avec la DSI et la sécurité des SI :

- authentification via l’annuaire institutionnel ;
- gestion stricte des sessions et time-out ;
- audit trail complet ;
- cloisonnement des rôles et des accès ;
- chiffrement des flux et des données ;
- hébergement conforme ;
- gestion des sauvegardes ;
- journalisation ;
- analyse de risque SSI ;
- conformité RGPD ;
- validation des contenus métier et gouvernance documentaire.

---

## Architecture actuelle

Le prototype actuel est volontairement léger pour faciliter la démonstration :

- application web front-end ;
- logique embarquée côté client ;
- prototype livré dans un fichier principal unique ;
- dépendances React chargées côté navigateur ;
- données de démonstration intégrées.

Cette architecture est adaptée à une **preuve de concept**, mais pas à un déploiement hospitalier en production sans refonte partielle.

---

## Déploiement de démonstration

### Option simple
Ouvrir le prototype dans un navigateur moderne.

### Option DSI / démonstration interne
Publier le front-end sur un serveur web interne (par exemple Nginx ou Apache) derrière le réseau hospitalier.

### Option cible
Faire évoluer le prototype vers une architecture client / serveur avec :
- authentification institutionnelle ;
- API applicative ;
- base de données ;
- traçabilité ;
- connecteurs SIH.

---

## Feuille de route proposée

### Phase 1 — Validation métier
- démonstration aux équipes de RI ;
- validation du parcours cible ;
- recueil des besoins DSI et sécurité ;
- priorisation des interfaces.

### Phase 2 — Industrialisation
- séparation front-end / back-end ;
- gestion des utilisateurs ;
- persistance des données ;
- audit ;
- sécurité ;
- documentation technique.

### Phase 3 — Intégration établissement
- SSO ;
- interfaçage SIH ;
- environnement pilote ;
- recette ;
- déploiement progressif.

---

## Licence proposée

### Recommandation
Pour un projet que l’on souhaite **présenter à une DSI tout en conservant une capacité de valorisation**, la stratégie recommandée est :

**Business Source License 1.1 (BSL 1.1)** pour le **code applicatif développé par l’auteur**, avec :

- usage libre pour l’évaluation, la démonstration et les tests non productifs ;
- possibilité d’un **Additional Use Grant** pour un pilote limité ;
- licence commerciale distincte pour un déploiement de production ou une réutilisation étendue ;
- conservation d’une vraie capacité de monétisation.

### Important
Le dépôt doit distinguer clairement :

1. **le code original RadioRI** ;
2. **les contenus tiers** (fiches patients, contenus documentaires, marques, textes externes).

Les contenus tiers ne doivent **pas** être relicenciés automatiquement sous la licence du code s’ils ne vous appartiennent pas.

### Recommandation pratique avant diffusion large
- conserver dans le dépôt uniquement le code et les contenus dont vous détenez les droits ;
- remplacer les contenus tiers copiés par des **liens vers les sources officielles** ;
- ajouter un fichier `NOTICE` listant les contenus tiers et leurs titulaires de droits ;
- prévoir une licence commerciale courte pour les usages de production.

---

## Avertissement réglementaire

RadioRI est présenté comme un **outil numérique de coordination de parcours et d’organisation métier**.

Le prototype n’est **pas** présenté comme un dispositif médical marqué CE, ni comme un outil autonome d’aide au diagnostic.

Toute utilisation en production dans un environnement hospitalier suppose :

- validation des contenus médicaux ;
- validation SSI ;
- validation juridique et RGPD ;
- gouvernance produit ;
- cadrage réglementaire selon les usages retenus.

---

## Pourquoi ce projet peut intéresser l’AP-HP

- il répond à un besoin métier concret ;
- il cible un secteur à forte coordination ;
- il est compréhensible rapidement en démonstration ;
- il peut servir de base à un pilote limité ;
- il est compatible avec une trajectoire d’industrialisation progressive.

---

## Contact / partenariat

Pour une démonstration, un pilote, une discussion d’intégration ou une licence de déploiement, merci de contacter l’auteur du projet.

---

## Résumé en une phrase

**RadioRI est un prototype applicatif de coordination de la radiologie interventionnelle, conçu pour structurer les demandes, améliorer la traçabilité et préparer une intégration hospitalière industrialisable.**
