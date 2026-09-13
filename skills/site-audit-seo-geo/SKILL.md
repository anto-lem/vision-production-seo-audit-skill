---
name: site-audit-seo-geo
description: Méthodologie complète et obligatoire pour réaliser un audit SEO + GEO/AEO (visibilité dans les réponses d'IA) d'un site web, en combinant les données Semrush (MCP) et des vérifications techniques manuelles. Utilise ce skill dès qu'on te demande d'auditer un site, de faire un état des lieux SEO, une analyse de visibilité en ligne, une comparaison avec des concurrents, un rapport pour un client d'agence, ou de vérifier la présence d'une marque dans ChatGPT/Perplexity/Gemini/AI Overviews — même si la demande semble ne porter que sur un seul aspect ("juste le SEO technique", "juste les backlinks"). Ce skill force à couvrir toutes les phases d'un audit complet et à documenter explicitement ce qui a été vérifié, pour qu'aucun axe important ne soit oublié.
---

# Audit de site web — SEO technique, on-page, contenu, backlinks, concurrence et GEO/AEO

## Pourquoi ce skill existe

Un audit fait "à l'instinct" saute presque toujours quelque chose : soit la partie technique est négligée au profit du contenu, soit personne ne va vérifier comment le site apparaît (ou n'apparaît pas) dans les réponses des IA génératives. Ce skill sert de garde-fou : une checklist en phases, avec pour chacune les outils Semrush à appeler, les vérifications manuelles à faire, et les seuils à comparer. Le but n'est pas de suivre les étapes de façon mécanique, mais de s'assurer qu'aucun axe n'est *silencieusement* ignoré — s'il y a une bonne raison de sauter une phase (site sans e-commerce, marché non couvert par Semrush, etc.), il faut le dire explicitement dans le rapport plutôt que de ne rien écrire.

## Avant de commencer : collecter le contexte

Ne lance pas les outils sans avoir clarifié :

1. **Domaine cible** (URL complète, avec ou sans www — vérifier lequel est canonique).
2. **Marché / langue** → détermine la `database` Semrush à utiliser (ex. `ca`, `us`, `fr`). Par défaut `us` seulement si rien n'indique un marché francophone/canadien ; pour un client basé au Québec, utiliser `ca` et confirmer si le marché visé est plutôt francophone.
3. **2 à 4 concurrents** — si l'utilisateur n'en donne pas, les identifier via `competitors_research` avant d'aller plus loin (ne pas deviner à l'œil).
4. **Mots-clés ou objectifs prioritaires** si connus (sinon, ils ressortiront des recherches de mots-clés en phase 3).
5. **Objectif du site** (génération de leads, e-commerce, notoriété locale) — influence l'importance relative de chaque section (ex. le SEO local compte plus pour une entreprise de services locaux).

Si une info manque et bloque une phase (ex. impossible de savoir quel marché cibler), pose la question plutôt que de deviner.

## Règle de gating — ne pas sauter de phase

Tiens à jour un tableau de suivi (dans ta réponse ou un fichier de travail) avec une ligne par phase :

| Phase | Statut | Preuve / source |
|---|---|---|
| 1. Vue d'ensemble & positionnement | ✅ / ⏳ / N/A (pourquoi) | |
| 2. SEO technique | | |
| 3. On-page & contenu | | |
| 4. Backlinks & autorité | | |
| 5. Concurrence | | |
| 6. GEO/AEO (visibilité IA) | | |

**Ne produis le rapport final que lorsque chaque ligne est à ✅ ou marquée N/A avec une justification écrite.** Si un outil Semrush renvoie une erreur, un quota dépassé, ou aucune donnée (domaine trop récent, trafic trop faible), écris-le explicitement dans le rapport — ne comble jamais un trou de données en inventant un chiffre.

## Phase 1 — Vue d'ensemble & positionnement

Objectif : avoir une photo globale avant de creuser.

- `domain_overview` sur le domaine cible (et sur chaque concurrent) : trafic organique estimé, nombre de mots-clés positionnés, Authority Score, répartition organique/payant.
- `traffic_overview` pour la tendance de trafic sur les 6-12 derniers mois (croissance, chute, saisonnalité).
- Noter les 3-5 chiffres clés qui serviront de résumé exécutif en tête du rapport.

## Phase 2 — SEO technique

Voir [references/technical-seo-checklist.md](references/technical-seo-checklist.md) pour le détail complet (crawlabilité/indexation, Core Web Vitals, HTTPS/sécurité, mobile-friendliness, architecture/maillage interne, données structurées, hreflang).

Outil principal : `site_audit` (lancer ou relire le dernier crawl du projet Semrush, passer en revue les thematic reports : Crawlability, HTTPS, Site Performance, Internal Linking, International SEO). Compléter par des vérifications manuelles directes sur le site (WebFetch sur `robots.txt`, `sitemap.xml`, une page type pour inspecter les balises).

## Phase 3 — On-page & contenu

Voir [references/onpage-content-checklist.md](references/onpage-content-checklist.md) pour le détail (titles, meta descriptions, structure Hn, alt text, qualité/E-E-A-T du contenu, cannibalisation, maillage interne sortant).

Outils : `organic_research` (positions actuelles et pages qui rankent déjà), `keyword_research` (volume, difficulté, intention pour les mots-clés cibles et les opportunités), `get_report_schema` + `execute_report` si un rapport de keyword gap est nécessaire.

## Phase 4 — Backlinks & autorité

Voir [references/backlinks-competition-checklist.md](references/backlinks-competition-checklist.md).

Outil principal : `backlinks_research` (overview, domaines référents, ancres, liens toxiques, tendance sur 6-12 mois).

## Phase 5 — Concurrence

Même fichier de référence que la phase 4 : [references/backlinks-competition-checklist.md](references/backlinks-competition-checklist.md).

Outils : `competitors_research`, `position_tracking` (si un projet Semrush existe déjà pour ce domaine), `traffic_overview` en comparaison directe avec les concurrents identifiés en phase 1.

## Phase 6 — GEO/AEO : visibilité dans les réponses d'IA

Voir [references/geo-aeo-checklist.md](references/geo-aeo-checklist.md) — **cette phase est manuelle et ne doit jamais être sautée** même si Semrush ne couvre pas ce point directement. Elle consiste à tester des prompts réalistes dans plusieurs IA génératives et à documenter si/comment la marque y est citée.

## Rapport final

Utilise le gabarit exact décrit dans [references/report-template.md](references/report-template.md) : résumé exécutif, constats classés par priorité (Critique / Élevé / Moyen / Faible), séparation quick wins vs actions long terme, et un score global par axe.

Avant de livrer le rapport, relis le tableau de gating ci-dessus : si une phase n'est pas ✅ ou N/A justifiée, complète-la d'abord.
