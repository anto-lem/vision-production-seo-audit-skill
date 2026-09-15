# Vision Production — Agent d'audit numérique complet

Ce repo contient un **agent Claude Code** : un agent autonome qui fait l'audit numérique complet d'une entreprise — site web, réseaux sociaux, réputation en ligne, SEO technique, on-page/contenu, backlinks, concurrence, et GEO/AEO (visibilité dans les réponses d'IA type ChatGPT/Perplexity/AI Overviews).

Il démarre avec très peu d'information : **le nom de l'entreprise, son site web, et ses réseaux sociaux.** Tout le reste (marché, concurrents, mots-clés), il le déduit lui-même — et documente ses hypothèses dans le rapport plutôt que de bloquer en attendant plus de contexte.

Le but : n'importe quelle instance de Claude Code connectée au MCP Semrush peut invoquer cet agent pour obtenir un audit complet, sans rien sauter — que ce soit pour un client de l'agence ou pour Vision Production elle-même.

L'agent se trouve dans [`agents/entreprise-audit-complet.md`](agents/entreprise-audit-complet.md) — un seul fichier autonome (pas de dépendances externes à cloner ailleurs).

## Pourquoi un agent plutôt qu'un skill

La première version de cet outil était un skill (des instructions suivies dans le fil de conversation principal). On est passé à un agent parce que le besoin a changé : maintenant, on veut donner un minimum d'info (nom + site + réseaux) et laisser l'outil aller chercher tout le reste tout seul — recherche web sur les réseaux sociaux, la réputation, les concurrents — sans repasser par l'utilisateur à chaque étape. Un agent tourne dans son propre espace de travail et revient seulement avec le rapport fini, ce qui garde aussi la conversation principale de l'admin de l'agence propre (pas noyée sous des dizaines d'appels d'outils bruts).

L'agent n'a **pas** de liste d'outils restreinte dans sa configuration (`tools:` n'est volontairement pas défini) — il hérite de tous les outils disponibles dans la session qui l'invoque. Ça évite un piège technique : si on avait figé une liste d'outils précise, ça aurait dû inclure le nom technique exact des outils Semrush, qui contient un identifiant propre à chaque installation MCP — et ça aurait cassé si l'agence a le MCP Semrush branché différemment d'ici.

## Comment l'installer — c'est un vrai plugin

Ce repo est structuré comme un plugin Claude Code (`.claude-plugin/plugin.json` + `.claude-plugin/marketplace.json`) — pas besoin de cloner le repo à la main ni de copier de fichier soi-même. Dans Claude Code (ou Cowork, qui utilise le même système de plugins), taper :

```
/plugin marketplace add anto-lem/vision-production-seo-audit-skill
/plugin install vision-production-seo-audit-skill@vision-production-seo-audit-skill
```

Le repo étant **privé**, il faut que la personne qui installe ait accès en lecture au repo GitHub (Antoine doit l'ajouter comme collaborateur sur `anto-lem/vision-production-seo-audit-skill`) et que git/`gh` soit authentifié sur sa machine avec ce compte — sinon la commande échoue à l'étape du clone, pas silencieusement.

Une fois installé, l'agent apparaît directement dans la liste des agents disponibles — aucune étape manuelle supplémentaire, et ça marche pareil pour tout le monde à l'agence.

### Mettre à jour le plugin plus tard

Après une modification du repo (nouvelle version poussée sur `main`) :

```
/plugin marketplace update vision-production-seo-audit-skill
```

### Si `/plugin` n'est pas disponible (ancienne version de Claude Code)

Repli manuel, équivalent mais sans le système de plugin :

```bash
git clone https://github.com/anto-lem/vision-production-seo-audit-skill.git
mkdir -p ~/.claude/agents
cp vision-production-seo-audit-skill/agents/entreprise-audit-complet.md ~/.claude/agents/entreprise-audit-complet.md
```

Mise à jour équivalente : `git pull` puis re-copier le fichier par-dessus l'ancien.

## Utilisation

Une fois installé, demander à ce Claude Code (avec le MCP Semrush connecté) — par exemple *"fais-moi un audit complet de [Nom de l'entreprise], site web [url], Instagram/Facebook [liens]"*. L'agent se déclenche automatiquement, tourne de façon autonome, et revient avec un rapport en deux volets :

- **Volet vente** — score visuel, 2-3 problèmes traduits en impact business chiffré, opportunité chiffrée, objections/réponses. Pensé pour qu'un vendeur qui n'y connaît rien en SEO puisse le présenter en appel.
- **Volet exécution** — constats précis (URLs/profils exacts, données exactes), plan d'action priorisé, et une checklist de prérequis (accès Search Console, Analytics, CMS, hébergement, réseaux sociaux) pour que la personne qui prend le mandat démarre sans refaire de découverte.

## Structure du repo

```
.claude-plugin/
├── plugin.json        ← manifest du plugin (nom, description, auteur, licence)
└── marketplace.json   ← permet d'installer directement depuis ce repo GitHub
agents/
└── entreprise-audit-complet.md   ← l'agent complet, un seul fichier autonome
```

## Partager l'accès à quelqu'un d'autre à l'agence

Le repo est privé — pour qu'une autre personne (à l'interne, comme un contractant de confiance) puisse faire `/plugin marketplace add`, elle doit être ajoutée comme collaborateur : Settings → Collaborators sur la page GitHub du repo, ou `gh repo add-collaborator anto-lem/vision-production-seo-audit-skill <son-username-github>`. Sans ça, la commande d'installation échoue à l'authentification même si elle connaît le nom du repo.
