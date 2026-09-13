# Gabarit du rapport final

Ce rapport a deux publics, à deux moments différents, et doit servir les deux sans qu'aucun ne doive redemander de l'information :

- **Le vendeur**, en appel avec un prospect, avant signature — a besoin de peu de jargon, d'un score simple à lire en quelques secondes, et de constats traduits en impact business chiffré (méthode complète dans [sales-framing.md](sales-framing.md)).
- **La personne qui exécute**, une fois le contrat signé — a besoin de l'inverse : précision totale (URLs exactes, données exactes, sources citées) pour démarrer dès le premier jour sans repasser par une phase de découverte.

**Ne mélange jamais les deux registres dans une même phrase.** Le Volet 1 est volontairement simple et orienté valeur ; le Volet 2 est volontairement précis et technique. Les deux racontent la même réalité à deux niveaux de détail — le Volet 2 est la preuve détaillée derrière chaque affirmation simplifiée du Volet 1. Ne pas remplir artificiellement une section vide, mais ne jamais l'omettre : si une phase n'a rien donné de significatif, l'écrire ("SEO technique : aucun problème critique détecté, site en bon état sur ce plan").

---

## Volet 1 — Pour la vente

```markdown
# Audit de [Nom du site] — ce qu'on a trouvé

## En bref
2-3 phrases, zéro jargon : l'état général du site, le problème le plus coûteux,
l'opportunité la plus évidente. Le vendeur doit pouvoir lire ça 30 secondes avant
un appel et être prêt à en parler.

## Score global
| Axe | 🟢🟡🔴 | En une phrase, sans jargon |
|---|---|---|
| Technique (vitesse, indexation) | | |
| Contenu | | |
| Autorité / confiance (backlinks) | | |
| Face aux concurrents | | |
| Visibilité dans les IA (ChatGPT, Perplexity, etc.) | | |

## Les problèmes qui coûtent le plus cher
Se limiter à 2-3 — trop de problèmes d'un coup dilue l'urgence au lieu de la créer.
Pour chacun (méthode de traduction dans sales-framing.md) :
- **Le problème**, en une phrase simple.
- **Ce que ça coûte**, chiffré si la donnée le permet (trafic perdu, mots-clés où
  un concurrent apparaît à sa place, tendance qui se dégrade).
- **Ce qu'on ferait**, en une phrase, sans détail d'exécution.

## L'opportunité chiffrée
Ex. "Vos concurrents [X] et [Y] captent environ [N] recherches/mois sur des mots-clés
que vous ne couvrez pas du tout." — la donnée qui justifie le prix du mandat, pas un
argument générique du type "vous devriez faire du SEO".

## Objections probables et comment y répondre
2-4 objections propres à CE prospect (pas génériques), avec la donnée de l'audit qui
les désamorce. Voir sales-framing.md pour la méthode.
```

## Volet 2 — Dossier d'exécution (post-signature)

```markdown
# Audit technique — [Nom du site]
Date : [date] · Domaine : [domaine] · Marché analysé : [database Semrush]
Concurrents comparés : [liste]

## Constats détaillés
### 🔴 Critique — à corriger immédiatement
### 🟠 Élevé — à traiter dans le mois
### 🟡 Moyen — à planifier dans le trimestre
### ⚪ Faible — optimisation, bonus

Pour chaque constat : quoi, URL exacte de la ou des pages concernées, preuve (quel
outil Semrush ou quelle vérification manuelle), impact estimé, effort estimé. Jamais
d'approximation — la personne qui exécute ne doit jamais avoir à redemander
"où exactement ?" ou "sur quelle base ?".

## Plan d'action
| Action | Priorité | Effort estimé | Impact attendu | Accès/info requis |
|---|---|---|---|---|

Trier pour faire ressortir en premier les actions à fort impact / faible effort
(les mêmes quick wins déjà évoqués dans le Volet 1, mais ici avec le détail complet).

## Prérequis pour démarrer
Ce qu'il faut avoir obtenu du client avant la première journée de travail, pour ne
pas reperdre de temps en découverte après la signature. Cocher/adapter selon ce que
révèlent les constats ci-dessus — ne pas demander un accès qui ne sert à aucune
action priorisée :
- [ ] Accès Google Search Console
- [ ] Accès Google Analytics (ou autre outil d'analytics en place)
- [ ] Accès admin du CMS (préciser lequel : WordPress, Webflow, Shopify, autre)
- [ ] Accès hébergement/DNS, si des changements techniques sont prévus
  (redirections, HTTPS, configuration serveur)
- [ ] Accès Google Business Profile, si du SEO local fait partie du plan
- [ ] Contact chez le client qui approuve le contenu (textes, publications)

## Annexe — tableau de gating de l'audit
Reprendre le tableau de suivi des 6 phases (voir SKILL.md) tel qu'il a été rempli,
pour montrer explicitement ce qui a été couvert et ce qui a été volontairement
exclu (avec la raison).

## Annexe — tableau de visibilité IA (GEO/AEO)
Le tableau prompt × IA détaillé dans geo-aeo-checklist.md.
```

## Règles de rédaction

- **Volet 1** : jamais de jargon SEO non expliqué (pas de "Core Web Vitals", "canonical", "Authority Score" sans traduction en langage courant) ; toujours ramener à une conséquence business (trafic, leads, ventes, image) ; chiffrer dès que la donnée le permet.
- **Volet 2** : jamais d'approximation — URL exacte, donnée exacte, source citée pour chaque constat.
- Chiffrer quand c'est possible plutôt que rester qualitatif ("le trafic organique a baissé de 18% sur 6 mois" plutôt que "le trafic semble en baisse").
- Test avant de livrer : un vendeur qui ne connaît rien au SEO peut-il présenter le Volet 1 sans se tromper ? Une personne qui prend le mandat peut-elle commencer à travailler avec seulement le Volet 2, sans revenir poser de question ? Si l'un des deux échoue, le rapport n'est pas fini.
