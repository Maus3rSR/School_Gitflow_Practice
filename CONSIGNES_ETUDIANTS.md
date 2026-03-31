# 🚀 Atelier GitFlow — Agence de Voyages Intergalactiques

## Contexte de la mission

Votre équipe (3–5 personnes) vient d'être recrutée par **GalaxyTrip**, une agence de voyages intergalactiques en pleine expansion. Votre mission : préparer le contenu du site web pour le lancement de la version 1.0.0, gérer un incident en production, et maintenir un historique Git propre selon le workflow GitFlow.

**Attention** : Pas de code à écrire ! Vous travaillez uniquement sur du contenu texte (Markdown).

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

## �️ Phase A — Initialisation (fondations)

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

## ✅ Livrables finaux

À la fin de l'atelier, votre dépôt GitHub doit contenir :

### Branches

- `main` (avec v1.0.0 et v1.0.1)
- `develop` (à jour avec tous les merges)

### Tags

- `v1.0.0` sur main
- `v1.0.1` sur main

### Fichiers

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

### Historique Git propre

- Pas de commits directs sur `main` (sauf merges)
- Features mergées dans `develop`
- Release et hotfix correctement intégrés
- Conflit résolu proprement
- Revert visible dans l'historique

---

## 🎓 Conseils

- **Communiquez** : synchronisez-vous régulièrement (`git fetch`, `git pull`)
- **Vérifiez** : utilisez `git log --oneline --graph --all` pour visualiser l'historique
- **Organisez-vous** : désignez un intégrateur pour éviter les conflits
- **CLI ou GUI** : utilisez l'outil de votre choix (VSCode, GitKraken, Sourcetree, CLI...)

---

## 🚀 Bon voyage intergalactique !

Que la force du Git soit avec vous. 🌌
