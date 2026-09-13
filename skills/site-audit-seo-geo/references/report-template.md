# Gabarit du rapport final

Utiliser cette structure exacte pour livrer un audit. Adapter la longueur de chaque section au volume de constats réels — ne pas remplir artificiellement une section vide, mais ne jamais l'omettre : si une phase n'a rien donné de significatif, l'écrire ("SEO technique : aucun problème critique détecté, site en bon état sur ce plan").

```markdown
# Audit SEO & GEO — [Nom du site / client]
Date : [date] · Domaine : [domaine] · Marché analysé : [database Semrush utilisée]
Concurrents comparés : [liste]

## Résumé exécutif
3 à 5 phrases : où en est le site aujourd'hui, les 2-3 problèmes les plus importants,
et l'opportunité la plus prometteuse. Doit pouvoir se lire seul, sans le reste du rapport.

## Score global par axe
| Axe | Score (/10 ou 🟢🟡🔴) | En une phrase |
|---|---|---|
| SEO technique | | |
| On-page & contenu | | |
| Backlinks & autorité | | |
| Position vs concurrents | | |
| Visibilité IA (GEO/AEO) | | |

## Constats détaillés

### 🔴 Critique — à corriger immédiatement
Problèmes qui bloquent l'indexation, cassent l'expérience utilisateur, ou font perdre
du trafic/des conversions de façon active. Pour chaque constat : quoi, où (URL/page),
preuve (donnée Semrush ou vérification manuelle), impact estimé.

### 🟠 Élevé — à traiter dans le mois
### 🟡 Moyen — à planifier dans le trimestre
### ⚪ Faible — optimisation, bonus

(Répéter la structure quoi/où/preuve/impact pour chaque priorité.)

## Quick wins vs actions long terme

| Action | Priorité | Effort estimé | Impact attendu |
|---|---|---|---|

Trier la table pour faire ressortir en premier les actions à fort impact / faible effort.

## Annexe — tableau de gating de l'audit
Reprendre le tableau de suivi des 6 phases (voir SKILL.md) tel qu'il a été rempli,
pour que le client/l'équipe voie explicitement ce qui a été couvert et ce qui a été
volontairement exclu (avec la raison).

## Annexe — tableau de visibilité IA (GEO/AEO)
Le tableau prompt × IA détaillé dans references/geo-aeo-checklist.md.
```

## Règles de rédaction

- Chaque constat cite sa source (quel outil Semrush, quelle vérification manuelle) — jamais une affirmation non sourcée.
- Chiffrer quand c'est possible (pourcentages, positions, volumes) plutôt que rester qualitatif ("le trafic organique a baissé de 18% sur 6 mois" plutôt que "le trafic semble en baisse").
- Écrire pour un lecteur qui n'est pas forcément expert SEO : expliquer brièvement le "pourquoi ça compte" pour chaque constat critique, pas seulement le "quoi".
