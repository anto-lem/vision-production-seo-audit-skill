# On-page & contenu — checklist détaillée

Sélectionner un échantillon représentatif avant de commencer : la page d'accueil, les 2-3 pages "argent" (services/produits principaux, celles qui génèrent des leads ou des ventes), et 2-3 articles de blog/contenu représentatifs. Auditer chacune individuellement plutôt que de généraliser à partir d'une seule page.

## Pour chaque page de l'échantillon

- **Title tag** : unique sur le site, 50-60 caractères environ (au-delà, Google tronque), contient le mot-clé cible sans sur-optimisation, formulé pour donner envie de cliquer.
- **Meta description** : unique, 120-158 caractères environ, résume la valeur de la page et incite au clic (pas juste une liste de mots-clés).
- **Structure des titres** : un seul `H1` par page, hiérarchie logique des `H2`/`H3` (pas de saut de niveau, pas de Hn utilisé juste pour le style visuel).
- **Présence du mot-clé cible** : dans le H1, dans le premier paragraphe, dans l'URL (si raisonnable) — sans bourrage de mots-clés.
- **Images** : attribut `alt` descriptif (pas vide, pas juste le nom de fichier), noms de fichiers propres, format optimisé (WebP/AVIF plutôt que JPEG/PNG non compressés), lazy loading sur les images hors écran initial.
- **Qualité et profondeur du contenu (E-E-A-T)** : comparer la longueur et la profondeur du contenu à ce qui rank déjà en position 1-3 pour le même mot-clé ; vérifier la présence d'un auteur identifié avec expertise pertinente, de sources/citations pour les affirmations factuelles, d'une date de publication et de mise à jour visible.
- **Maillage interne sortant** : la page fait-elle des liens pertinents vers d'autres pages du site (pages produits/services liées, articles connexes) avec une ancre descriptive ?
- **Appel à l'action** : clair et cohérent avec l'objectif de la page (contact, achat, inscription).

## Recherche de mots-clés et opportunités

- `organic_research` sur le domaine cible : quelles pages rankent déjà, sur quels mots-clés, à quelle position, avec quel volume de trafic estimé.
- `keyword_research` sur les mots-clés cibles (fournis par le client ou déduits de son activité) : volume de recherche, difficulté (Keyword Difficulty), intention de recherche (informationnelle/transactionnelle/navigationnelle/commerciale) — s'assurer que le contenu existant correspond à l'intention réelle du mot-clé visé.
- Repérer les opportunités : mots-clés pertinents à fort volume / faible-moyenne difficulté que le site ne couvre pas encore, ou pour lesquels il rank en page 2-3 (positions 11-30, souvent les plus faciles à faire progresser en page 1).

## Cannibalisation de mots-clés

Vérifier via `organic_research` si plusieurs pages du site rankent pour le même mot-clé principal — c'est un signal de cannibalisation qui dilue l'autorité au lieu de la concentrer sur une seule page forte. Si détecté, le signaler explicitement avec les URLs concernées.

## Rapport de keyword gap (optionnel mais recommandé)

Si `get_report_schema` + `execute_report` permettent un rapport de type "keyword gap" entre le domaine cible et les concurrents identifiés en phase 1, l'utiliser pour lister les mots-clés sur lesquels les concurrents rankent mais pas le client — base directe pour des recommandations de contenu concrètes.
