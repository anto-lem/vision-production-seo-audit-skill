# SEO technique — checklist détaillée

Pour chaque section : ce qu'il faut vérifier, avec quoi, et le seuil qui distingue un point correct d'un point à corriger.

## 1. Crawlabilité & indexation

- `robots.txt` accessible et ne bloque pas de ressources/pages importantes par erreur.
- `sitemap.xml` présent, valide, à jour (pas de pages 404/redirigées dedans), et déclaré dans `robots.txt` et Search Console.
- Balises `canonical` cohérentes : une seule version canonique par contenu, pas de boucles ni de canonicals pointant vers une page différente sans raison.
- Comparer le nombre de pages indexées (`site:domaine.com` sur Google, ou données Search Console si disponibles) au nombre de pages réelles du site — un écart important dans un sens (peu de pages indexées) ou l'autre (beaucoup plus de pages indexées que de pages réelles = doublons/paramètres) est un signal à creuser.
- Chaînes de redirection (plus de 1 saut), redirections en boucle, redirections temporaires (302) utilisées là où une 301 permanente serait correcte.
- Erreurs 4xx/5xx détectées par le crawl — prioriser celles sur des pages avec du trafic ou des liens entrants.
- Paramètres d'URL générant du contenu dupliqué (tri, filtres, tracking) sans canonical ni gestion appropriée.

Outil Semrush : `site_audit`, thematic report **Crawlability**.

## 2. Performance & Core Web Vitals

Seuils Google (mobile ET desktop, à vérifier séparément — mobile est presque toujours pire) :

- **LCP** (Largest Contentful Paint) : bon ≤ 2.5s, à améliorer 2.5-4s, mauvais > 4s.
- **INP** (Interaction to Next Paint) : bon ≤ 200ms, à améliorer 200-500ms, mauvais > 500ms.
- **CLS** (Cumulative Layout Shift) : bon ≤ 0.1, à améliorer 0.1-0.25, mauvais > 0.25.

Sources : thematic report **Site Performance** de `site_audit`, complété si possible par PageSpeed Insights / CrUX sur les pages les plus visitées (pas seulement la page d'accueil).

Causes fréquentes à signaler si détectées : images non compressées/non dimensionnées, polices web bloquantes, scripts tiers (chat, analytics, pixels pub) chargés de façon bloquante, absence de mise en cache/CDN.

## 3. Sécurité & configuration

- HTTPS actif sur tout le site, aucune ressource en HTTP (contenu mixte) sur les pages HTTPS.
- Certificat valide, pas d'avertissement navigateur.
- Redirection HTTP → HTTPS systématique et en 301.
- En-tête HSTS présent (bonus, pas bloquant pour un audit standard).

Thematic report **HTTPS** de `site_audit`.

## 4. Mobile-friendliness

- Le site est responsive (pas de version mobile séparée non maintenue).
- Balise `viewport` présente et correcte.
- Texte lisible sans zoom, zones cliquables (boutons, liens) suffisamment espacées pour le tactile.
- Pas d'élément qui déborde horizontalement sur mobile (scroll horizontal involontaire).

Vérification manuelle recommandée : ouvrir 2-3 pages clés en émulation mobile.

## 5. Architecture & maillage interne

- Profondeur de clic depuis la page d'accueil : idéalement ≤ 3 clics pour toute page importante.
- Pages orphelines (aucun lien interne entrant) détectées par le crawl — si elles sont importantes pour le business, c'est un problème.
- Liens internes cassés (pointant vers des 404).
- Présence de breadcrumbs (fil d'Ariane) sur les sites avec plusieurs niveaux de profondeur.
- Ancrage des liens internes : éviter le "cliquez ici" générique, préférer une ancre descriptive avec le mot-clé pertinent.

Thematic report **Internal Linking** de `site_audit`.

## 6. Données structurées (schema.org)

- Présence de `Organization` ou `LocalBusiness` (nom, logo, coordonnées, réseaux sociaux) sur les pages clés.
- `BreadcrumbList` si le site a des breadcrumbs visuels.
- Type adapté au contenu : `Article`/`BlogPosting` pour un blog, `Product` + `Review`/`AggregateRating` pour de l'e-commerce, `FAQPage` si des FAQ existent (voir aussi la phase GEO/AEO — c'est un point de recoupement important).
- Valider l'absence d'erreurs/avertissements (Rich Results Test de Google ou équivalent) — un schema mal formé ne sert à rien et peut même nuire.

## 7. Internationalisation (si applicable)

- Balises `hreflang` correctes et réciproques si le site a plusieurs versions linguistiques/régionales.
- Pas de conflit entre `hreflang` et `canonical`.

Thematic report **International SEO** de `site_audit` (à ignorer proprement, en le notant N/A, si le site est mono-marché/mono-langue).
