# GEO/AEO — visibilité dans les réponses d'IA générative

## Pourquoi c'est différent du SEO classique

Une IA générative (ChatGPT, Perplexity, Gemini, Google AI Overviews, Claude) ne renvoie pas une liste de liens à cliquer : elle synthétise une réponse directe, en citant (ou non) des sources. Être *cité ou mentionné correctement* dans cette réponse compte autant — parfois plus, pour les requêtes où l'utilisateur ne clique jamais plus loin — que d'être bien classé dans les résultats classiques. Un site peut très bien être en position 1-3 sur Google et complètement absent des réponses d'une IA, ou pire, y être mentionné avec des informations fausses ou obsolètes.

Semrush n'a pas (ou pas toujours, selon le plan) un outil dédié équivalent pour ce point — vérifier via `get_report_schema` si un rapport de type "AI visibility" ou équivalent existe pour le compte connecté, mais **ne jamais sauter cette phase si l'outil n'est pas disponible** : le test manuel décrit ci-dessous reste obligatoire.

## Étape 1 — Construire une liste de prompts réalistes

Rédiger 8 à 12 prompts que poserait un client potentiel réel, pas des recherches de mots-clés déguisées. S'inspirer des catégories suivantes :

- **Recommandation directe** : "meilleure [métier/service] à [ville/région]", "je cherche un [type de prestataire] pour [besoin précis]".
- **Réputation/avis** : "[nom de la marque] avis", "est-ce que [marque] est fiable".
- **Comparaison** : "[marque] vs [concurrent identifié]", "différence entre [marque] et [concurrent]".
- **Informationnelle liée à l'expertise du client** : une question que son contenu de blog est censé couvrir, pour voir si c'est le site du client qui sert de source à la réponse de l'IA ou un concurrent/un tiers.

## Étape 2 — Tester chaque prompt dans plusieurs IA

Tester au minimum : ChatGPT, Perplexity, Google (AI Overviews sur la requête équivalente), et si pertinent Gemini/Claude. Pour chaque combinaison prompt × IA, noter :

- La marque est-elle citée ? (oui / non / citée mais mal nommée ou confondue avec un tiers)
- Quelle description l'IA donne-t-elle de la marque ? Est-elle exacte et à jour ?
- Quelles sources l'IA cite-t-elle à l'appui de sa réponse ? Le site du client en fait-il partie ?
- Si un concurrent est cité à la place, lequel, et via quelle source ?

Consigner ça sous forme de tableau dans le rapport :

| Prompt testé | IA | Marque citée | Description donnée | Sources citées | Écart avec la réalité |
|---|---|---|---|---|---|

## Étape 3 — Diagnostiquer les facteurs qui influencent la citabilité

Une fois les résultats collectés, croiser avec l'état du site pour expliquer les résultats plutôt que de simplement les constater :

- **Contenu structuré en réponses directes** : le contenu répond-il clairement à une question en 2-3 phrases quelque part sur la page (les IA génératives extraient plus facilement une réponse nette qu'un paragraphe marketing vague) ?
- **Données structurées** : présence de `FAQPage`, `Organization`, `HowTo` selon le contenu — un recoupement direct avec la phase 2 (SEO technique).
- **Présence chiffrée/citable** : statistiques, études de cas, chiffres concrets — les IA privilégient les contenus qui apportent une information vérifiable plutôt qu'une simple affirmation.
- **Cohérence de la marque sur des sources tierces** que les IA citent souvent : profil Google Business Profile, avis Google/annuaires sectoriels, mentions presse, Reddit/forums spécialisés, Wikipedia si applicable. Une incohérence (nom, adresse, description) entre ces sources et le site nuit à la confiance que l'IA accorde à l'information.
- **Fraîcheur** : contenu daté et mis à jour récemment vs contenu qui n'a pas bougé depuis des années.
- **E-E-A-T perçu** : auteur identifié avec expertise démontrée, page "à propos" claire, transparence sur qui est l'entreprise.

## Ce qu'il faut livrer dans le rapport

Le tableau de résultats (étape 2), suivi d'un diagnostic court reliant les manques constatés (étape 3) à des actions concrètes — par exemple "la marque n'apparaît dans aucune des 4 IA testées pour les prompts de recommandation locale ; aucune donnée structurée FAQPage n'est présente et le profil Google Business Profile n'est pas à jour (adresse différente du site) → corriger la cohérence NAP en priorité et ajouter une page FAQ structurée sur les 3 questions les plus posées par les clients."
