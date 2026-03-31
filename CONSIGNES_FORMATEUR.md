# 🎓 Consignes Formateur — Atelier GitFlow

## Vue d'ensemble

**Durée** : 1h30 à 2h  
**Format** : Groupes de 3–5 étudiants  
**Plateforme** : GitHub (remote obligatoire)  
**Thématique** : Agence de voyages intergalactiques (GalaxyTrip)  
**Niveau** : Intermédiaire (fondamentaux Git acquis)

---

## 🎯 Objectifs pédagogiques

Les étudiants doivent maîtriser :
1. Le workflow **GitFlow** (main, develop, feature, release, hotfix)
2. La collaboration sans Pull Requests (synchronisation manuelle)
3. La résolution de conflits
4. Les corrections propres (revert, hotfix)
5. Le versionnement SemVer et les tags

---

## 📋 Préparation (avant l'atelier)

### Matériel à fournir
- [ ] Document `CONSIGNES_ETUDIANTS.md` (distribué à chaque groupe)
- [ ] Accès GitHub pour tous les étudiants
- [ ] Tableau blanc ou slides pour expliquer GitFlow (5–10 min)

### Prérequis étudiants
- Git installé (CLI ou GUI au choix)
- Compte GitHub configuré
- Connaissances de base : clone, commit, push, pull, branch, merge

### Organisation des groupes
- Constituer les groupes (3–5 personnes) **avant** l'atelier
- Désigner 1 membre par groupe pour créer le dépôt GitHub
- Chaque groupe nomme son dépôt : `galaxytrip-gitflow-<nom-groupe>`

---

## ⏱️ Déroulé recommandé

### Introduction (10 min)
1. Présenter le contexte : agence GalaxyTrip, pas de code, uniquement Markdown
2. Expliquer GitFlow (schéma au tableau) :
   - `main` = production
   - `develop` = intégration
   - `feature/*` = développement
   - `release/*` = préparation livraison
   - `hotfix/*` = correction urgente prod
3. Rappeler les conventions (Conventional Commits, SemVer)
4. Distribuer les consignes étudiants

### Phase A — Initialisation (15 min)
**Tâches 1–4** : Création dépôt, branches main/develop, clonage, docs fondateurs

**Votre rôle** :
- Vérifier que chaque groupe a bien créé `main` et `develop`
- Aider au clonage si besoin
- Valider que les docs fondateurs sont mergés dans `develop`

### Phase B — Features parallèles (20 min)
**Tâches 5–8** : 3 features (homepage, pricing, FAQ) + intégration dans develop

**Votre rôle** :
- Encourager la parallélisation (3 membres travaillent en même temps)
- Vérifier que les branches feature sont bien nommées (`feature/<prenom>-<sujet>`)
- Valider que l'intégration dans `develop` utilise des merge commits (`--no-ff`)

### Phase C — Conflit (15 min)
**Tâches 9–10** : Conflit volontaire sur README + résolution

**Votre rôle** :
- **C'est le moment clé** : observer comment les groupes gèrent le conflit
- Ne pas intervenir trop vite (laisser chercher 5 min)
- Aider à identifier les marqueurs de conflit (`<<<<<<<`, `=======`, `>>>>>>>`)
- Valider que la résolution est cohérente et committée proprement

### Phase D — Release (20 min)
**Tâches 11–15** : Création release/1.0.0, CHANGELOG, version, correction, merge + tag

**Votre rôle** :
- Vérifier que la branche `release/1.0.0` part bien de `develop`
- Valider le CHANGELOG et la mise à jour de version
- **Important** : vérifier que le tag `v1.0.0` est bien créé sur `main`
- Vérifier que la release est réintégrée dans `develop`

### Phase E — Hotfix (15 min)
**Tâches 16–18** : Incident prod (prix Lune), hotfix/1.0.1, merge + tag

**Votre rôle** :
- Vérifier que le hotfix part bien de `main` (pas de develop)
- Valider le tag `v1.0.1`
- Vérifier la réintégration dans `develop`

### Phase F — Revert (10 min)
**Tâches 19–20** : Erreur volontaire + annulation propre avec revert

**Votre rôle** :
- Insister sur `git revert` (pas `git reset`)
- Expliquer pourquoi (historique public, collaboration)

### Conclusion (5 min)
- Faire un tour des groupes pour valider les livrables
- Débrief collectif : difficultés rencontrées, leçons apprises

---

## ✅ Checklist de vérification rapide

Pour chaque groupe, vérifier en 2 minutes :

### 1. Graphe Git
```bash
git log --oneline --decorate --graph --all
```
**Attendu** :
- Historique en forme de "branches" (pas linéaire)
- Merges visibles de features → develop
- Merges de release et hotfix → main
- Revert visible sur develop

### 2. Tags
```bash
git tag --list
```
**Attendu** :
- `v1.0.0`
- `v1.0.1`

Vérifier les tags :
```bash
git show v1.0.0
git show v1.0.1
```

### 3. Branches
```bash
git branch -a
```
**Attendu** :
- `main`
- `develop`
- (optionnel : branches feature/release/hotfix si non supprimées)

### 4. Fichiers
```bash
ls -R
```
**Attendu** :
```
README.md
CHANGELOG.md
docs/vision.md
docs/glossary.md
docs/faq.md
content/homepage.md
content/pricing.md
```

### 5. Discipline GitFlow
- Pas de commits directs sur `main` (seulement merges de release/hotfix)
- Features mergées dans `develop`
- Hotfix parti de `main` et réintégré dans `develop`

---

## 🚨 Problèmes fréquents et solutions

### "On a oublié de créer develop"
→ Créer maintenant depuis main : `git checkout -b develop main`

### "Le conflit nous bloque"
→ Montrer les marqueurs, expliquer comment choisir/combiner, puis `git add` + `git commit`

### "On a fait un commit direct sur main"
→ Pas grave pour l'exercice, mais noter l'erreur et expliquer pourquoi c'est interdit en prod

### "Le tag n'apparaît pas sur GitHub"
→ Oublié de push : `git push origin v1.0.0`

### "On a fait git reset au lieu de revert"
→ Si pas encore pushé : OK, refaire avec revert. Si pushé : expliquer le problème (historique réécrit)

### "Les branches feature sont encore sur le remote"
→ Optionnel de les supprimer, mais bon moment pour expliquer le nettoyage

---

## 🎯 Points d'attention pédagogiques

### Insister sur
1. **Conventions** : Conventional Commits (type: message)
2. **Merge commits** : `--no-ff` pour garder l'historique lisible
3. **Tags** : Toujours sur `main`, jamais sur `develop`
4. **Hotfix** : Part de `main`, pas de `develop`
5. **Revert vs Reset** : Revert pour historique public

### Valoriser
- Les groupes qui s'organisent bien (intégrateur désigné)
- Les messages de commit clairs et conventionnels
- La résolution de conflit collaborative
- L'historique Git propre et lisible

### Éviter
- De donner la solution trop vite (laisser chercher)
- De pénaliser les erreurs (c'est un exercice d'apprentissage)
- De se focaliser sur l'outil (CLI vs GUI) : l'important est le résultat

---

## 📊 Variantes (ajustements possibles)

### Plus facile (≈ 60 min)
- Supprimer Phase C (conflit)
- Supprimer Phase F (revert)
- Réduire le nombre de features (2 au lieu de 3)

### Plus difficile (≈ 3h)
- Ajouter un **rebase** : avant de merger une feature, la rebaser sur develop
- Ajouter un **cherry-pick** : sélectionner un commit de develop vers release
- Ajouter un **git bisect** : préparer une "régression" et la faire chercher

### Autre thématique
Le format fonctionne avec n'importe quelle thématique fun :
- Restaurant de cuisine moléculaire
- Festival de musique intergalactique
- Refuge pour créatures fantastiques
- Agence de détectives paranormaux

---

## 📝 Notes pour la correction

### Barème suggéré (si évaluation)
- Branches et tags présents : 30%
- Historique GitFlow respecté : 30%
- Conventions de commits : 20%
- Résolution de conflit : 10%
- Revert propre : 10%

### Correction rapide (5 min/groupe)
1. Clone du repo
2. `git log --graph --all --oneline` → capture d'écran
3. `git tag --list` → vérifier v1.0.0 et v1.0.1
4. Vérifier fichiers présents
5. Chercher le commit de résolution de conflit
6. Chercher le commit de revert

---

## 🎓 Débriefing collectif (questions à poser)

1. Quelle phase a été la plus difficile ? (souvent : conflit ou hotfix)
2. Avez-vous utilisé CLI ou GUI ? Pourquoi ?
3. Comment vous êtes-vous organisés en équipe ?
4. Qu'avez-vous appris sur GitFlow ?
5. Quelles erreurs avez-vous faites ? Comment les avez-vous corrigées ?

---

## 📚 Ressources complémentaires

- [GitFlow original (Vincent Driessen)](https://nvie.com/posts/a-successful-git-branching-model/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [SemVer](https://semver.org/)
- [Atlassian Git tutorials](https://www.atlassian.com/git/tutorials)

---

**Bon atelier ! 🚀**
