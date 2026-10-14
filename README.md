# Padel N One — site vitrine & réservation

Complexe padel 6 pistes + bar La Bulle · 1 rue Eugène Freyssinet, 51470 Saint-Memmie · 06 30 29 13 07 · [@padel_n_one](https://www.instagram.com/padel_n_one/)

Site statique en **un seul fichier** (`index.html`) : HTML, CSS et JS inline, aucune dépendance, aucun build.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | Le site complet (intro animée, hero 3D, sections, module de réservation démo) |
| `og-image.jpg` | Visuel de partage (WhatsApp, Facebook, LinkedIn) — 1200×630 |
| `robots.txt` / `sitemap.xml` | Référencement |
| `padel-n-one.mp4` | **À ajouter** : vidéo du hero (H.264, 1080p, < 8 Mo, 10-20 s, sans son) |

## Mise en ligne

**Vercel** : New Project → importer le dépôt → Framework « Other » → Deploy. Aucun réglage.
**GitHub Pages** : Settings → Pages → Branch `main` / root.

Puis remplacer `https://www.padelnone.fr/` par le vrai domaine dans `index.html` (balises `canonical`, `og:*`, JSON-LD), `robots.txt` et `sitemap.xml`.

## À valider avec le club

Tout est centralisé dans l'objet `CONFIG` en bas de `index.html` :
- tarifs par piste (`CONFIG.prices`) et règle heures pleines (`CONFIG.isPeak`)
- horaires (`CONFIG.open` / `CONFIG.close`)
- type de piste (`CONFIG.courts[].type`, ex. « Indoor »)

Et dans le HTML : SIREN et hébergeur (mentions légales), horaires du bar.

## Réservation

Le module actuel est une **démonstration** (données stockées dans le navigateur du visiteur, aucun paiement). Avant production : brancher Playtomic, BalleJaune ou un backend + Stripe.

## Animations

- **Intro** : jouée une fois par session, bouton « Passer », désactivée si l'utilisateur a choisi « réduire les animations ».
- **Hero** : piste 3D en canvas avec échanges réalistes (rebonds, vitres, ombre). Se met en pause hors écran et s'arrête dès que la vidéo est disponible.
