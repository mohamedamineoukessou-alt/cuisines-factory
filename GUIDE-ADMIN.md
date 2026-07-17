# Espace d'administration — Cuisines Factory

Ce site dispose d'un espace d'administration (**Decap CMS**) qui permet d'ajouter,
réordonner ou supprimer des **images de galerie** et des **sliders avant/après**
sans toucher au code.

Adresse de l'admin, une fois le site en ligne : **`https://VOTRE-SITE.netlify.app/admin/`**

---

## 1. Mise en service (à faire UNE SEULE FOIS)

L'admin a besoin que le site soit hébergé sur **GitHub + Netlify connectés**
(le glisser-déposer Netlify ne suffit plus). Étapes :

1. **Créer un compte GitHub** (gratuit) sur https://github.com si vous n'en avez pas.
2. **Créer un dépôt** (« New repository », nom au choix, ex. `cuisines-factory`).
   Puis, dans le dépôt, bouton **« Add file » → « Upload files »** et déposez
   **tout le contenu de ce dossier** (index.html, admin/, content/, assets/,
   images/, _headers, netlify.toml, etc.). Validez (« Commit changes »).
3. **Connecter Netlify au dépôt** : sur https://app.netlify.com →
   **« Add new site » → « Import an existing project » → GitHub** → choisissez le dépôt.
   Laissez le build vide (le `netlify.toml` s'en occupe) → **Deploy**.
4. **Activer Identity** : dans le site Netlify → onglet **« Identity »** →
   **« Enable Identity »**. Puis **« Registration »** → passez en **« Invite only »**.
5. **Activer Git Gateway** : toujours dans Identity → **« Services »** →
   **« Enable Git Gateway »**.
6. **Vous inviter** : Identity → **« Invite users »** → entrez votre e-mail.
   Vous recevrez un mail → cliquez le lien → définissez un mot de passe.
7. C'est prêt : allez sur **`.../admin/`** et connectez-vous.

> Astuce : dans `admin/config.yml`, remplacez `cuisinesfactory.netlify.app`
> (lignes `site_url` / `display_url`) par votre vraie adresse Netlify.

---

## 2. Utilisation au quotidien

1. Ouvrez `https://VOTRE-SITE.netlify.app/admin/` et connectez-vous.
2. Choisissez une rubrique dans le menu de gauche :
   - **Galerie · Cuisines** / **Galerie · Vitrines** → la liste des photos.
   - **Sliders · Design 3D** / **Sliders · Avant / Après** → les comparateurs (2 images chacun).
3. Pour **ajouter** : bouton « Add … », puis **glissez une image** (ou choisissez-en
   une déjà présente). Pour **réordonner** : glissez les lignes. Pour **supprimer** :
   l'icône de suppression de la ligne.
4. Cliquez **« Publish »** (Publier). Le site se met à jour tout seul en 1–2 minutes.

---

## 3. Important — qualité des images

Le CMS **n'optimise pas** les images : n'uploadez pas des photos de 8 Mo sorties
du téléphone/appareil, sinon le site s'alourdit. Avant d'uploader, réduisez-les à
**~1600 px de large** et compressez-les (ex. https://squoosh.app, gratuit).

- Les **cuisines** sont plutôt en format portrait/vertical.
- Les **vitrines** en carré ou portrait.
- Pour un **slider**, les deux images (avant/après ou plan 3D/réalisation) doivent
  cadrer la même scène pour un rendu propre.

---

## 4. Où vit le contenu (pour info)

- Les listes sont stockées dans les fichiers `content/*.json`.
- Les nouvelles images uploadées atterrissent dans `assets/uploads/`.
- Le site (`index.html`) lit ces fichiers au chargement ; s'ils manquent, il
  retombe sur un contenu par défaut intégré (le site ne casse jamais).

Le **design et la structure** du site restent modifiables par le code, en parallèle,
sans rien perdre de l'admin.
