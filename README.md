# Bodyscan.io — Landing page

Landing page statique (HTML/Tailwind/AOS/Supabase) pour Bodyscan.io.

## ⚠️ Avant de déployer

Ouvre `index.html`, cherche ces deux lignes (vers la fin du fichier, dans le `<script>`) :

```js
const SUPABASE_URL = 'https://VOTRE-PROJET.supabase.co';
const SUPABASE_ANON_KEY = 'VOTRE_CLE_ANON_PUBLIC';
```

Remplace-les par les vraies valeurs de ton projet Supabase :
**Dashboard Supabase → Project Settings → API → Project URL / anon public key**

Sans ça, le site s'affiche normalement mais la connexion/inscription ne fonctionnera pas.

## 🚀 Déployer en 5 minutes

### 1. Mettre le projet sur GitHub

```bash
git init
git add .
git commit -m "Landing page Bodyscan.io"
```

Crée un nouveau repo sur [github.com/new](https://github.com/new) (par exemple `bodyscan-io`), puis :

```bash
git remote add origin https://github.com/TON-USERNAME/bodyscan-io.git
git branch -M main
git push -u origin main
```

### 2. Déployer sur Vercel

1. Va sur [vercel.com/new](https://vercel.com/new)
2. Connecte ton compte GitHub si ce n'est pas déjà fait
3. Sélectionne le repo `bodyscan-io`
4. Vercel détecte automatiquement un site statique — laisse les réglages par défaut
5. Clique sur **Deploy**

Ton site sera en ligne sur une URL du type `bodyscan-io.vercel.app` en moins d'une minute.

### 3. Brancher ton domaine bodyscan.io

Dans le dashboard Vercel du projet → **Settings → Domains** → ajoute `bodyscan.io`, puis suis les instructions pour configurer les DNS chez ton registrar (en général un enregistrement `A` ou `CNAME`).

## 🔐 Configurer l'authentification (Supabase)

Une fois ton URL finale connue (Vercel ou ton domaine) :

1. Dashboard Supabase → **Authentication → URL Configuration**
   - **Site URL** : `https://bodyscan.io` (ou ton URL Vercel)
   - **Redirect URLs** : ajoute la même URL
2. Dashboard Supabase → **Authentication → Providers**
   - Active **Google** et **Apple**, Supabase t'affiche l'URL de callback à coller dans Google Cloud Console / Apple Developer

## 🛠️ Tester en local avant de déployer (optionnel)

```bash
npm run dev
```

Ouvre `http://localhost:3000`.
