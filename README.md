# Vision Production — Skill d'audit SEO/GEO

Ce repo contient un **skill Claude Code** : une méthodologie de référence, complète et en checklist, pour réaliser un audit de site web (SEO technique, on-page, contenu, backlinks, concurrence, et GEO/AEO — visibilité dans les réponses d'IA type ChatGPT/Perplexity/AI Overviews).

Le but : n'importe quelle instance de Claude Code connectée au MCP Semrush peut se référer à ce skill pour faire un audit complet, sans rien sauter — que ce soit pour un client de l'agence ou pour Vision Production elle-même.

Le skill se trouve dans [`skills/site-audit-seo-geo/`](skills/site-audit-seo-geo/SKILL.md).

## Comment le brancher sur le Claude Code de l'admin de l'agence

Le plus simple : demander directement au Claude Code de l'agence de faire l'installation. Dans une conversation avec lui, coller ceci :

> Clone le repo `anto-lem/vision-production-seo-audit-skill`, puis copie le dossier `skills/site-audit-seo-geo` dans `~/.claude/skills/site-audit-seo-geo` (crée le dossier `~/.claude/skills/` s'il n'existe pas). Ça installera le skill d'audit SEO/GEO pour toutes mes conversations.

Il fera ça tout seul (clone privé — il faut que `gh`/git soit authentifié sur le compte qui a accès au repo, sinon il te le dira).

### Étapes manuelles équivalentes (si besoin de le faire à la main)

```bash
git clone https://github.com/anto-lem/vision-production-seo-audit-skill.git
mkdir -p ~/.claude/skills
cp -r vision-production-seo-audit-skill/skills/site-audit-seo-geo ~/.claude/skills/site-audit-seo-geo
```

Une fois copié, le skill apparaît automatiquement dans la liste des skills disponibles de ce Claude Code (pas besoin de redémarrer quoi que ce soit de spécial — au pire, ouvrir une nouvelle conversation).

### Mettre à jour le skill plus tard

Si le contenu du skill change dans ce repo (nouvelle version des checklists), il faut re-copier le dossier par-dessus l'ancien :

```bash
cd vision-production-seo-audit-skill && git pull
cp -r skills/site-audit-seo-geo ~/.claude/skills/site-audit-seo-geo
```

## Utilisation

Une fois installé, il suffit de demander à ce Claude Code (avec le MCP Semrush connecté) de faire un audit d'un site — par exemple *"fais-moi un audit SEO complet du site de [client], compare-le à [concurrents]"*. Le skill se déclenche automatiquement et force à couvrir les 6 phases : vue d'ensemble, SEO technique, on-page/contenu, backlinks, concurrence, et visibilité IA (GEO/AEO) — avec un rapport final structuré par priorité (Critique/Élevé/Moyen/Faible).

## Structure du repo

```
skills/site-audit-seo-geo/
├── SKILL.md                                    ← méthodologie principale, les 6 phases
└── references/
    ├── technical-seo-checklist.md              ← SEO technique (crawl, Core Web Vitals, HTTPS, mobile, maillage, schema)
    ├── onpage-content-checklist.md              ← titles/meta/Hn, qualité de contenu, mots-clés, cannibalisation
    ├── backlinks-competition-checklist.md       ← backlinks, autorité, comparaison concurrents
    ├── geo-aeo-checklist.md                     ← visibilité dans ChatGPT/Perplexity/AI Overviews
    └── report-template.md                       ← gabarit exact du rapport final
```
