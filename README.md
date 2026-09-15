# Vision Production — Agent d'audit numérique complet

Ce repo contient un **agent Claude Code** : un agent autonome qui fait l'audit numérique complet d'une entreprise — site web, réseaux sociaux, réputation en ligne, SEO technique, on-page/contenu, backlinks, concurrence, et GEO/AEO (visibilité dans les réponses d'IA type ChatGPT/Perplexity/AI Overviews).

Il démarre avec très peu d'information : **le nom de l'entreprise, son site web, et ses réseaux sociaux.** Tout le reste (marché, concurrents, mots-clés), il le déduit lui-même — et documente ses hypothèses dans le rapport plutôt que de bloquer en attendant plus de contexte.

Le but : n'importe quelle instance de Claude Code connectée au MCP Semrush peut invoquer cet agent pour obtenir un audit complet, sans rien sauter — que ce soit pour un client de l'agence ou pour Vision Production elle-même.

L'agent se trouve dans [`agents/entreprise-audit-complet.md`](agents/entreprise-audit-complet.md) — un seul fichier autonome (pas de dépendances externes à cloner ailleurs).

## Pourquoi un agent plutôt qu'un skill

La première version de cet outil était un skill (des instructions suivies dans le fil de conversation principal). On est passé à un agent parce que le besoin a changé : maintenant, on veut donner un minimum d'info (nom + site + réseaux) et laisser l'outil aller chercher tout le reste tout seul — recherche web sur les réseaux sociaux, la réputation, les concurrents — sans repasser par l'utilisateur à chaque étape. Un agent tourne dans son propre espace de travail et revient seulement avec le rapport fini, ce qui garde aussi la conversation principale de l'admin de l'agence propre (pas noyée sous des dizaines d'appels d'outils bruts).

L'agent n'a **pas** de liste d'outils restreinte dans sa configuration (`tools:` n'est volontairement pas défini) — il hérite de tous les outils disponibles dans la session qui l'invoque. Ça évite un piège technique : si on avait figé une liste d'outils précise, ça aurait dû inclure le nom technique exact des outils Semrush, qui contient un identifiant propre à chaque installation MCP — et ça aurait cassé si l'agence a le MCP Semrush branché différemment d'ici.

## Comment le brancher sur le Claude Code de l'admin de l'agence

Le plus simple : demander directement au Claude Code de l'agence de faire l'installation. Dans une conversation avec lui, coller ceci :

> Clone le repo `anto-lem/vision-production-seo-audit-skill`, puis copie le fichier `agents/entreprise-audit-complet.md` dans `~/.claude/agents/entreprise-audit-complet.md` (crée le dossier `~/.claude/agents/` s'il n'existe pas). Ça installera l'agent d'audit numérique complet pour toutes mes conversations.

Il fera ça tout seul (clone privé — il faut que `gh`/git soit authentifié sur le compte qui a accès au repo, sinon il te le dira).

### Étapes manuelles équivalentes (si besoin de le faire à la main)

```bash
git clone https://github.com/anto-lem/vision-production-seo-audit-skill.git
mkdir -p ~/.claude/agents
cp vision-production-seo-audit-skill/agents/entreprise-audit-complet.md ~/.claude/agents/entreprise-audit-complet.md
```

Une fois copié, l'agent apparaît automatiquement dans la liste des agents disponibles de ce Claude Code (au pire, ouvrir une nouvelle conversation).

### Mettre à jour l'agent plus tard

```bash
cd vision-production-seo-audit-skill && git pull
cp agents/entreprise-audit-complet.md ~/.claude/agents/entreprise-audit-complet.md
```

## Utilisation

Une fois installé, demander à ce Claude Code (avec le MCP Semrush connecté) — par exemple *"fais-moi un audit complet de [Nom de l'entreprise], site web [url], Instagram/Facebook [liens]"*. L'agent se déclenche automatiquement, tourne de façon autonome, et revient avec un rapport en deux volets :

- **Volet vente** — score visuel, 2-3 problèmes traduits en impact business chiffré, opportunité chiffrée, objections/réponses. Pensé pour qu'un vendeur qui n'y connaît rien en SEO puisse le présenter en appel.
- **Volet exécution** — constats précis (URLs/profils exacts, données exactes), plan d'action priorisé, et une checklist de prérequis (accès Search Console, Analytics, CMS, hébergement, réseaux sociaux) pour que la personne qui prend le mandat démarre sans refaire de découverte.

## Structure du repo

```
agents/
└── entreprise-audit-complet.md   ← l'agent complet, un seul fichier autonome
```
