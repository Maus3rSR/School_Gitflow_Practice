# 🚀 Atelier GitFlow — GalaxyTrip

Bienvenue dans cet atelier pratique où tu vas maîtriser le workflow GitFlow à travers un scénario d'agence de voyages intergalactiques !

## 📖 Description

Dans cet atelier, tu vas pratiquer Git et GitFlow **sans écrire de code**, uniquement avec des fichiers Markdown. Tu travailleras en groupe (3–5 personnes) sur un projet commun hébergé sur GitHub, sans utiliser de Pull Requests.

**Thématique** : GalaxyTrip, une agence de voyages vers Mars, la Lune, Saturne et au-delà ! 🌌

**Durée** : 1h30 à 2h

---

## 🎯 Ce que tu vas apprendre

- Maîtriser le cycle GitFlow (main, develop, feature, release, hotfix)
- Collaborer sans Pull Requests (synchronisation manuelle)
- Résoudre des conflits Git
- Corriger/annuler des erreurs proprement (revert, hotfix)
- Livrer avec tags et versionnement SemVer

---

## 🚀 Démarrage rapide

1. **Lire les consignes** : `CONSIGNES_ETUDIANTS.md`
2. **Former un groupe** de 3–5 personnes
3. **Créer un dépôt GitHub (si pas déjà fait)** : `galaxytrip-gitflow-<nom-groupe>`
4. **Suivre les 20 tâches** décrites dans les consignes

---

## 🛠️ Workflow GitFlow (rappel)

### Branches

- **main** : production (tags v1.0.0, v1.0.1...)
- **develop** : intégration des fonctionnalités
- **feature/\*** : développement de fonctionnalités
- **release/\*** : préparation de livraison
- **hotfix/\*** : correction urgente en production

---

## 📝 Conventions

### Commits (Conventional Commits)

Format : `<type>: <message>`

Types : `feat`, `fix`, `docs`, `content`, `release`, `chore`, `revert`

Exemples :

```
docs: add glossary
content: add pricing page
fix: correct typo in FAQ
release: prepare 1.0.0
```

### Versionnement (SemVer)

Format : `MAJOR.MINOR.PATCH`

Exemples : `1.0.0`, `1.0.1`, `2.0.0`

Tags sur `main` : `v1.0.0`, `v1.0.1`

---

## ✅ Ce que tu dois livrer

À la fin de l'atelier, ton dépôt GitHub doit contenir :

### Branches

- `main` (avec merges de release et hotfix)
- `develop` (avec merges de features)

### Tags

- `v1.0.0` sur main
- `v1.0.1` sur main

### Fichiers

- `README.md`, `CHANGELOG.md`
- `docs/vision.md`, `docs/glossary.md`, `docs/faq.md`
- `content/homepage.md`, `content/pricing.md`

### Historique Git

- Pas de commits directs sur `main` (sauf merges)
- Features mergées dans `develop`
- Release et hotfix correctement intégrés
- Conflit résolu proprement
- Revert visible dans l'historique

---

## 🔍 Comment vérifier ton travail

Utilise ces commandes (ou l'interface GUI) pour t'assurer que tout est en ordre :

```bash
# Voir l'historique complet
git log --oneline --decorate --graph --all

# Lister les tags
git tag --list

# Voir les branches
git branch -a

# Vérifier un tag
git show v1.0.0
```

---

## 🎓 Ce dont tu as besoin

- Git installé sur ta machine (CLI ou GUI : VSCode, GitKraken, Sourcetree...)
- Un compte GitHub configuré
- Les bases de Git : clone, commit, push, pull, branch, merge

---

## 📖 Ressources utiles

Si tu veux approfondir tes connaissances :

- [GitFlow (Vincent Driessen)](https://nvie.com/posts/a-successful-git-branching-model/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [SemVer](https://semver.org/)
- [Git Documentation](https://git-scm.com/doc)

---

## 🌟 Pour aller plus loin

### Si tu trouves ça trop facile

- Essaie de rebaser tes features sur develop avant de les merger
- Utilise `git cherry-pick` pour sélectionner un commit spécifique
- Pratique `git bisect` pour trouver une régression

---

## 📧 Besoin d'aide ?

Si tu es bloqué pendant l'atelier, n'hésite pas à lever la main ou à demander à ton formateur !

---

**Bon voyage intergalactique ! 🚀✨**

_Que Git --force soit avec toi._
