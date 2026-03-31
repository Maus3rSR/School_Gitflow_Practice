# 🚀 Atelier GitFlow — Agence de Voyages Intergalactiques

## Contexte de la mission

Votre équipe (3–5 personnes) vient d'être recrutée par **GalaxyTrip**, une agence de voyages intergalactiques en pleine expansion. Votre mission : préparer le contenu du site web pour le lancement de la version 1.0.0, gérer un incident en production, et maintenir un historique Git propre selon le workflow GitFlow.

**Attention** : Pas de code à écrire ! Vous travaillez uniquement sur du contenu texte (Markdown).

---

## ⏱️ Durée et versions

### 📘 Atelier de base (1h30-2h)

**Phases A à F** — Tâches 1 à 20

- Initialisation GitFlow
- Features en parallèle
- Résolution de conflits
- Release et hotfix
- Revert

### 📗 Atelier avancé (3h-4h)

**Phases A à J** — Tâches 1 à 30

- Tout l'atelier de base
- Gestion avancée des branches (stash, amend, dépendances)
- Documentation collaborative
- Rebase et historique propre
- Debugging (bisect, blame, cherry-pick)

---

## 🎯 Objectifs pédagogiques

- Maîtriser le cycle **GitFlow** (main, develop, feature/_, release/_, hotfix/\*)
- Collaborer sans Pull Requests (synchronisation manuelle)
- Résoudre des conflits Git
- Corriger/annuler des erreurs proprement
- Livrer avec tags et versionnement SemVer

---

## 📋 Règles impératives

### Branches

- **main** : production (uniquement merges de release/hotfix)
- **develop** : intégration (features mergées ici)
- **feature/<prenom>-<sujet>** : développement de fonctionnalités
- **release/<version>** : préparation de livraison (ex: `release/1.0.0`)
- **hotfix/<version>** : correction urgente prod (ex: `hotfix/1.0.1`)

### Commits (Conventional Commits)

Format obligatoire : `<type>: <message court>`

**Types autorisés** :

- `feat` : nouvelle fonctionnalité
- `fix` : correction de bug
- `docs` : documentation
- `content` : ajout/modification de contenu
- `release` : préparation de version
- `chore` : tâches diverses

**Exemples** :

```
docs: add glossary of planets
content: add pricing for Mars trip
fix: correct typo in FAQ
release: prepare 1.0.0
```

### Versionnement (SemVer)

Format : `MAJOR.MINOR.PATCH` (ex: 1.0.0, 1.0.1)

- Tags sur **main** : `v1.0.0`, `v1.0.1`, etc.

### CHANGELOG

Le fichier `CHANGELOG.md` documente l'historique des versions. Format recommandé :

```markdown
# Changelog

## [1.0.1] - 2026-04-15

### Fixed

- Correction du prix du voyage lunaire

## [1.0.0] - 2026-03-31

### Added

- Page d'accueil avec destinations
- Grille tarifaire complète
- FAQ pour les voyageurs

### Fixed

- Amélioration du slogan
```

### Interdictions

❌ Pas de commit direct sur `main` ou `develop` (sauf consigne explicite)  
❌ Pas de Pull Requests GitHub (synchronisation manuelle uniquement)

---

## 🛠️ Phase A — Initialisation (fondations)

### Tâche 1 : Création du dépôt

1. Créer un dépôt GitHub public nommé `galaxytrip-gitflow`
2. Ajouter un `README.md` minimal :

```markdown
# 🚀 GalaxyTrip — Voyages Intergalactiques

L'agence de voyages qui vous emmène au-delà des étoiles.

Version: dev
```

### Tâche 2 : Initialiser GitFlow

1. Créer la branche `main` (déjà faite par défaut)
2. Créer la branche `develop` depuis `main`
3. Pousser les deux branches sur GitHub
4. Définir `develop` comme branche par défaut dans les settings GitHub (optionnel)

### Tâche 3 : Clonage

Chaque membre clone le dépôt sur sa machine :

```bash
git clone <url-du-repo>
cd galaxytrip-gitflow
git branch -a  # Vérifier les branches
```

### Tâche 4 : Documents fondateurs

1. Créer une branche feature appropriée
2. Créer le dossier `docs/` avec :

**`docs/vision.md`** :

```markdown
# Vision GalaxyTrip

## Mission

Rendre les voyages spatiaux accessibles à tous les terriens.

## Valeurs

- Sécurité avant tout
- Exploration responsable
- Émerveillement garanti

## Objectifs 2026

- Lancer 50 vols vers Mars
- Ouvrir une station orbitale lunaire
- Proposer des croisières autour de Saturne
```

**`docs/glossary.md`** :

```markdown
# Glossaire Intergalactique

- **Parsec** : Unité de distance (3,26 années-lumière)
- **Gravité zéro** : Absence de pesanteur
- **Propulsion ionique** : Technologie de nos vaisseaux
- **Terraformation** : Rendre une planète habitable
- **Exoplanète** : Planète hors du système solaire
```

3. Faire un commit avec un message approprié (Conventional Commits)
4. Pousser la branche sur GitHub
5. Merger dans `develop` (sans PR, en local ou via un autre membre)

---

## 🚀 Phase B — Features en parallèle (collaboration)

### Tâche 5 : Page d'accueil

1. Créer une branche feature pour la page d'accueil depuis `develop`
2. Créer `content/homepage.md` :

```markdown
# Bienvenue chez GalaxyTrip ! 🌌

Envie d'évasion ? Nos destinations vous attendent :

- 🔴 **Mars** : Le rouge vous va si bien
- 🌙 **Lune** : Un classique indémodable
- 🪐 **Saturne** : Admirez les anneaux de près
- ⭐ **Alpha Centauri** : Pour les aventuriers

Réservez dès maintenant votre voyage de rêve !
```

3. Faire un commit avec un message approprié (Conventional Commits)
4. Pousser la branche

### Tâche 6 : Tarification

1. Créer une branche feature pour la tarification depuis `develop`
2. Créer `content/pricing.md` :

```markdown
# Nos Tarifs 💰

## Destinations populaires

| Destination    | Durée   | Prix (€)   | Niveau        |
| -------------- | ------- | ---------- | ------------- |
| Lune           | 3 jours | 50 000     | Débutant      |
| Mars           | 6 mois  | 500 000    | Intermédiaire |
| Saturne        | 2 ans   | 2 000 000  | Expert        |
| Alpha Centauri | 10 ans  | 10 000 000 | Légendaire    |

_Assurance cosmique incluse_
```

3. Faire un commit avec un message approprié (Conventional Commits)
4. Pousser la branche

### Tâche 7 : FAQ

1. Créer une branche feature pour la FAQ depuis `develop`
2. Créer `docs/faq.md` :

```markdown
# FAQ — Questions Fréquentes 🤔

## Dois-je être astronaute ?

Non ! Nos vols sont ouverts à tous (après examen médical).

## Que se passe-t-il en cas de panne ?

Nos vaisseaux ont 12 systèmes de secours redondants.

## Puis-je annuler mon voyage ?

Oui, jusqu'à 6 mois avant le départ (remboursement à 80%).

## Y a-t-il du WiFi dans l'espace ?

Oui, mais avec un ping de 20 minutes vers Mars.

## Que manger à bord ?

Menu gastronomique lyophilisé 5 étoiles.
```

3. Faire un commit avec un message approprié (Conventional Commits)
4. Pousser la branche

### Tâche 8 : Intégration dans develop

> 💡 **Astuce** : Désignez un membre "intégrateur" pour cette tâche et les suivantes.

1. Se placer sur `develop`
2. Merger les 3 features (homepage, pricing, faq) dans `develop`
3. Utiliser des **merge commits** (option `--no-ff`)

4. Pousser `develop`

---

## ⚔️ Phase C — Conflit volontaire + résolution

### Tâche 9 : Préparer le conflit

> 💡 **Organisation** : 2 membres doivent travailler en parallèle sur cette tâche.

**Membre 1** :

1. Créer une branche feature depuis `develop`
2. Modifier `README.md` (ligne 3) :

```markdown
L'agence de voyages qui vous emmène explorer l'univers infini.
```

3. Faire un commit avec un message approprié (Conventional Commits)
4. Pousser la branche

**Membre 2** :

1. Créer une branche feature depuis `develop`
2. Modifier `README.md` (ligne 3, même ligne !) :

```markdown
L'agence de voyages qui vous propulse vers les étoiles.
```

3. Faire un commit avec un message approprié (Conventional Commits)
4. Pousser la branche

### Tâche 10 : Créer et résoudre le conflit

1. Merger d'abord la première branche dans `develop` → OK
2. Tenter de merger la seconde branche dans `develop` → **CONFLIT !**
3. Résoudre le conflit en gardant une version cohérente (au choix, ou combiner)
4. Faire un commit de résolution avec un message approprié (Conventional Commits)
5. Pousser `develop`

---

## 📦 Phase D — Release (préparation livraison)

### Tâche 11 : Démarrer la release

1. Créer une branche release pour la version 1.0.0 depuis `develop`
2. Pousser la branche

### Tâche 12 : Préparer le CHANGELOG

1. Sur la branche release, créer `CHANGELOG.md` :

```markdown
# Changelog

## [1.0.0] - 2026-03-31

### Added

- Page d'accueil avec destinations principales
- Grille tarifaire complète
- FAQ pour les voyageurs
- Vision et glossaire de l'agence

### Fixed

- Amélioration du slogan
```

2. Faire un commit avec un message approprié (Conventional Commits)

### Tâche 13 : Mettre à jour la version

1. Modifier `README.md` (ligne "Version:") :

```markdown
Version: 1.0.0
```

2. Faire un commit avec un message approprié (Conventional Commits)

### Tâche 14 : Correction en release

1. Détecter une faute dans `content/pricing.md` (ex: "Assurance cosmique inclue" → "incluse")
2. Corriger sur la branche release
3. Faire un commit avec un message approprié (Conventional Commits)

### Tâche 15 : Finaliser la release

1. Merger la branche release dans `main` (avec `--no-ff`)
2. Créer le tag `v1.0.0` sur `main` avec un message descriptif
3. Pousser `main` et le tag sur GitHub
4. Merger la branche release (ou `main`) dans `develop` pour réintégrer les commits de release
5. Pousser `develop`

---

## 🚨 Phase E — Incident prod + Hotfix

### Tâche 16 : Détecter l'incident

Quelqu'un constate une **erreur critique** dans `content/pricing.md` en production :

- Le prix de la Lune est à 50 000 € au lieu de 5 000 € !

### Tâche 17 : Créer le hotfix

1. Créer une branche hotfix pour la version 1.0.1 depuis `main`
2. Corriger le prix de la Lune dans `content/pricing.md` (5 000 € au lieu de 50 000 €)

3. Faire un commit avec un message approprié (Conventional Commits)

### Tâche 18 : Finaliser le hotfix

1. Merger la branche hotfix dans `main`
2. Créer le tag `v1.0.1` avec un message descriptif
3. Pousser `main` et le tag
4. Merger la branche hotfix dans `develop` (pour réintégration)
5. Pousser `develop`
6. Mettre à jour `CHANGELOG.md` sur `develop` avec les corrections apportées

---

## 🔄 Phase F — Annulation propre

### Tâche 19 : Créer une erreur volontaire

1. Sur `develop`, modifier `docs/vision.md` : supprimer la section "Valeurs"
2. Faire un commit avec un message approprié (Conventional Commits)
3. Pousser `develop`

### Tâche 20 : Annuler avec revert

1. Constater l'erreur (la section Valeurs était importante !)
2. Annuler le commit avec `git revert` (PAS de reset)
3. Git créera automatiquement un message de revert, vous pouvez le personnaliser si nécessaire
4. Pousser `develop`

---

## 🔄 Phase G — Gestion avancée des branches

### Tâche 21 : Feature avec dépendance

> 💡 **Objectif** : Comprendre les dépendances entre features

1. Créer une branche feature pour ajouter `content/partners.md` (partenaires spatiaux)
2. Créer le fichier avec une liste de partenaires :

```markdown
# Nos Partenaires Spatiaux 🤝

- **SpaceX** : Fournisseur de fusées
- **NASA** : Expertise technique
- **ESA** : Coordination européenne
- **Blue Origin** : Vols suborbitaux
```

3. Faire un commit
4. Créer une **seconde branche feature** depuis la première (pas depuis develop) pour ajouter `content/testimonials.md`
5. Créer le fichier avec des témoignages clients :

```markdown
# Témoignages Clients ⭐

> "Un voyage inoubliable vers Mars !" - Jean D.

> "L'équipe GalaxyTrip est professionnelle et rassurante." - Marie L.

> "La vue de la Terre depuis l'espace... magique !" - Ahmed K.
```

6. Faire un commit
7. Merger la première feature (partners) dans `develop`
8. Merger la seconde feature (testimonials) dans `develop`
9. Pousser `develop`

### Tâche 22 : Stash — Sauver du travail en cours

> 💡 **Objectif** : Gérer une erreur de contexte avec git stash

1. Se placer sur `develop`
2. Commencer à modifier `README.md` (ajouter une ligne de description)
3. **STOP** — Réaliser que cette modification devrait être sur une branche feature !
4. Utiliser `git stash` pour sauvegarder le travail en cours
5. Créer une branche feature appropriée
6. Appliquer le stash avec `git stash pop`
7. Finaliser la modification et faire un commit
8. Merger dans `develop`

### Tâche 23 : Amend — Corriger un commit récent

> 💡 **Objectif** : Corriger un commit avant de le pousser

1. Sur une branche feature, créer `docs/safety.md` :

```markdown
# Sécurité à Bord 🛡️

## Équipement fourni

- Combinaison spatiale
- Casque avec communication
- Réserve d'oxygène (48h)

## Procédures d'urgence

- Évacuation rapide
- Capsule de sauvetage
- Contact permanent avec la Terre
```

2. Faire un commit avec une **faute volontaire** dans le message (ex: "docs: add safty guide")
3. Utiliser `git commit --amend` pour corriger le message
4. Pousser la branche et merger dans `develop`

---

## 📚 Phase H — Documentation collaborative

### Tâche 24 : Modifications parallèles sans conflit

> 💡 **Objectif** : Comprendre quand Git merge automatiquement

**2 membres travaillent en parallèle** :

**Membre 1** :

1. Créer une branche feature
2. Ajouter une section "Contact" à la fin de `README.md`
3. Faire un commit et pousser

**Membre 2** :

1. Créer une branche feature (depuis develop)
2. Modifier le début de `README.md` (changer la description ligne 3)
3. Faire un commit et pousser

**Intégrateur** :

1. Merger les deux features dans `develop`
2. Observer que Git merge automatiquement (pas de conflit car lignes différentes)
3. Pousser `develop`

### Tâche 25 : Enrichir la documentation

1. Créer une branche feature
2. Ajouter un fichier `AUTHORS.md` :

```markdown
# Contributeurs GalaxyTrip 👨‍🚀👩‍🚀

## Équipe de développement

- [Prénom 1] - Développeur
- [Prénom 2] - Développeur
- [Prénom 3] - Développeur
- [Prénom 4] - Intégrateur
- [Prénom 5] - Développeur

## Remerciements

Merci à tous les voyageurs intergalactiques qui nous font confiance !
```

3. Mettre à jour `README.md` pour ajouter un badge de version :

```markdown
# 🚀 GalaxyTrip — Voyages Intergalactiques

![Version](https://img.shields.io/badge/version-1.0.1-blue)

L'agence de voyages qui vous emmène au-delà des étoiles.
```

4. Faire un commit et merger dans `develop`

---

## 📦 Phase H-bis — Release 1.1.0

### Tâche 25-bis : Préparer la release 1.1.0

> 💡 **Objectif** : Livrer les nouvelles fonctionnalités (partners, testimonials, safety, AUTHORS)

1. Créer une branche release pour la version 1.1.0 depuis `develop`
2. Mettre à jour `CHANGELOG.md` :

```markdown
## [1.1.0] - 2026-04-01

### Added

- Page partenaires spatiaux
- Témoignages clients
- Guide de sécurité à bord
- Fichier des contributeurs
- Badge de version dans le README

### Changed

- Amélioration de la description du README
```

3. Mettre à jour le badge de version dans `README.md` (passer de 1.0.1 à 1.1.0)
4. Faire un commit
5. Merger la branche release dans `main`
6. Créer le tag `v1.1.0` sur `main` avec un message descriptif
7. Pousser `main` et le tag
8. Merger la branche release dans `develop`
9. Pousser `develop`

---

## 🔧 Phase I — Rebase et historique propre

### Tâche 26 : Rebase interactif — Nettoyer l'historique

> 💡 **Objectif** : Squash plusieurs commits en un seul

1. Créer une branche feature pour `content/destinations.md`
2. Faire **3 commits séparés** (un par destination) :
   - Commit 1 : Ajouter la section Mars
   - Commit 2 : Ajouter la section Jupiter
   - Commit 3 : Ajouter la section Titan

3. Utiliser `git rebase -i HEAD~3` pour squash les 3 commits en 1 seul
4. Réécrire le message de commit final
5. Pousser la branche
6. Merger dans `develop`

### Tâche 27 : Rebase sur develop — Maintenir une feature à jour

> 💡 **Objectif** : Rebaser une feature longue sur develop

**Simulation** :

1. Créer une branche feature `insurance` pour `content/insurance.md`
2. Faire un commit initial
3. **Pendant ce temps**, un autre membre ajoute du contenu sur `develop` et pousse
4. Rebaser la branche `insurance` sur le dernier `develop`
5. Résoudre les conflits éventuels
6. Finaliser la feature et merger dans `develop`

### Tâche 28 : Cherry-pick — Sélectionner un commit spécifique

> 💡 **Objectif** : Appliquer un commit d'une branche à une autre

**Scénario** : Pendant la préparation de la release 1.2.0, une correction importante est committée sur `develop`.

1. Créer une branche release pour la version 1.2.0 depuis `develop`
2. Pendant la release, un membre corrige une faute dans `docs/faq.md` sur `develop` et pousse
3. Identifier le hash de ce commit de correction
4. Sur la branche release 1.2.0, utiliser `git cherry-pick` pour appliquer uniquement ce commit
5. Vérifier que le commit apparaît sur la release avec un nouveau hash
6. **Ne pas finaliser cette release pour l'instant** (elle servira pour la Phase J)

---

## 🔍 Phase J — Debugging et investigation

### Tâche 29 : Git bisect — Trouver un commit fautif

> 💡 **Objectif** : Débugger avec git bisect

**Préparation** : Introduire volontairement une "régression"

1. Sur `develop`, modifier `content/pricing.md` : changer le prix de Mars à 5 000 000 € (erreur)
2. Faire un commit
3. Ajouter d'autres commits innocents (modifications de docs)

**Debugging** :

1. Constater que le prix de Mars est incorrect
2. Utiliser `git bisect start`
3. Marquer le commit actuel comme mauvais : `git bisect bad`
4. Marquer un ancien commit (avant l'erreur) comme bon : `git bisect good <hash>`
5. Git va proposer des commits à tester
6. Tester chaque commit et marquer `good` ou `bad`
7. Git identifiera le commit fautif
8. Terminer avec `git bisect reset`
9. Corriger l'erreur avec un nouveau commit

### Tâche 30 : Git blame et log — Investigation

> 💡 **Objectif** : Investiguer l'historique d'un fichier

1. Utiliser `git blame content/pricing.md` pour voir qui a modifié chaque ligne
2. Identifier la ligne avec le prix de la Lune
3. Utiliser `git log -p -- content/pricing.md` pour voir l'historique complet du fichier
4. Utiliser `git log --oneline --follow -- content/pricing.md` pour suivre les renommages
5. Documenter les découvertes dans un fichier `docs/investigation.md`

### Tâche 31 : Finaliser la release 1.2.0

> 💡 **Objectif** : Livrer les dernières fonctionnalités et corrections

1. Retourner sur la branche release 1.2.0 (créée à la Tâche 28)
2. Mettre à jour `CHANGELOG.md` :

```markdown
## [1.2.0] - 2026-04-05

### Added

- Page destinations détaillées (Mars, Jupiter, Titan)
- Assurance voyage spatiale

### Fixed

- Correction de fautes dans la FAQ
- Correction du prix de Mars (régression corrigée)
```

3. Mettre à jour le badge de version dans `README.md` (passer de 1.1.0 à 1.2.0)
4. Faire un commit
5. Merger la branche release dans `main`
6. Créer le tag `v1.2.0` sur `main` avec un message descriptif
7. Pousser `main` et le tag
8. Merger la branche release dans `develop`
9. Pousser `develop`

---

## ✅ Livrables finaux

À la fin de l'atelier, votre dépôt GitHub doit contenir :

### Branches

- `main` (avec v1.0.0, v1.0.1, v1.1.0 et v1.2.0)
- `develop` (à jour avec tous les merges)

### Tags

**Atelier de base** :

- `v1.0.0` sur main
- `v1.0.1` sur main

**Atelier avancé (en plus)** :

- `v1.1.0` sur main
- `v1.2.0` sur main

### Fichiers

**Atelier de base (Phases A-F)** :

```
README.md
CHANGELOG.md
docs/
  vision.md
  glossary.md
  faq.md
content/
  homepage.md
  pricing.md
```

**Atelier avancé (Phases G-J)** :

```
AUTHORS.md
docs/
  safety.md
  investigation.md
content/
  partners.md
  testimonials.md
  destinations.md
  insurance.md
```

### Historique Git propre

**Atelier de base** :

- Pas de commits directs sur `main` (sauf merges)
- Features mergées dans `develop`
- Release et hotfix correctement intégrés
- Conflit résolu proprement
- Revert visible dans l'historique

**Atelier avancé (en plus)** :

- Commits squashés avec rebase interactif
- Feature rebasée sur develop
- Cherry-pick appliqué sur release
- Bisect utilisé pour trouver une régression
- Stash utilisé pour sauver du travail

---

## 🎓 Conseils

- **Communiquez** : synchronisez-vous régulièrement (`git fetch`, `git pull`)
- **Vérifiez** : utilisez `git log --oneline --graph --all` pour visualiser l'historique
- **Organisez-vous** : désignez un intégrateur pour éviter les conflits
- **CLI ou GUI** : utilisez l'outil de votre choix (VSCode, GitKraken, Sourcetree, CLI...)

---

## 🚀 Bon voyage intergalactique !

Que la force du Git soit avec vous. 🌌
