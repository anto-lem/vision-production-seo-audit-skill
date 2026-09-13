# Backlinks, autorité & analyse concurrentielle — checklist détaillée

## Profil de liens du domaine cible

Outil : `backlinks_research`.

- Nombre total de domaines référents (referring domains) — plus significatif que le nombre brut de liens.
- Authority Score du domaine et son évolution si l'historique est disponible.
- Tendance sur 6-12 mois : gain net ou perte nette de domaines référents (une perte nette soutenue est un signal d'alerte, souvent liée à des liens qui expirent ou du désaveu).
- Ratio dofollow/nofollow — un ratio anormalement bas de dofollow peut limiter la transmission d'autorité.
- Répartition des ancres de liens : une sur-optimisation (trop d'ancres exact-match sur le même mot-clé) est un signal de risque plutôt qu'un atout, surtout si les liens ont été construits artificiellement.
- Liens toxiques/spammy détectés — évaluer s'ils représentent une part significative du profil (à signaler pour désaveu si oui).

## Comparaison avec les concurrents

Outils : `competitors_research`, `domain_overview` (déjà utilisé en phase 1, réutiliser les chiffres), `backlinks_research` sur chaque concurrent identifié.

- Comparer Authority Score et nombre de domaines référents du client vs 2-4 concurrents identifiés.
- Identifier le "backlink gap" : des domaines qui font des liens vers plusieurs concurrents mais pas vers le client — ce sont des cibles de prospection prioritaires (annuaires sectoriels, presse locale, partenaires, associations professionnelles).
- Vérifier que les concurrents choisis sont bien des concurrents *SEO* réels (ils rankent sur les mêmes mots-clés / dans le même espace de recherche), pas seulement des concurrents business perçus par le client — utiliser `competitors_research` pour confirmer ou ajuster la liste avant de conclure.

## Visibilité organique comparée

Outils : `traffic_overview`, `position_tracking` (si un projet Semrush existe déjà pour ce domaine et suit des mots-clés dans le temps).

- Comparer le trafic organique estimé du client vs chaque concurrent sur la même période.
- Si `position_tracking` est disponible, regarder l'évolution des positions sur les mots-clés suivis plutôt qu'une simple photo à l'instant T — une tendance qui se dégrade doit être signalée même si les positions actuelles semblent correctes.
- Si aucun projet de tracking n'existe, le noter dans le rapport comme une recommandation (mettre en place un suivi de positions sur les mots-clés prioritaires identifiés en phase 3).
