# Portfolio Minimaliste – Guide d’utilisation

## 📋 Vue d’ensemble
Portfolio statique (HTML/CSS) avec sections Hero, About, Projects, Skills et Contact. La section Projects supporte désormais des captures d’écran, une description détaillée et un lien vers le projet. La section Contact inclut des icônes SVG (Gmail, GitHub, LinkedIn) et un bouton pour télécharger le CV.

## 🗂️ Structure des fichiers

```
ia-folio/
├── index.html          # Structure HTML du site
├── style.css           # Styles et effets visuels (glassmorphism, animations, responsive)
├── README.md           # Ce guide
├── captures_prompt/    # captures d’écran des prompts
└── cv/                 # 
```

## ✏️ Personnaliser le contenu

### Projets (captures + description + lien)
- Les cartes projets utilisent une image `img.project-image` recadrée en carré automatiquement (sans déformation) via CSS (`aspect-ratio: 1/1` et `object-fit: cover`).
- Remplacez les images `project1.jpg`, `project2.jpg`, etc. par vos fichiers (ex: `captures_prompt/power4.jpg`) et mettez à jour `src` dans `index.html`.
- Exemple de bloc projet à copier/modifier dans `index.html`:

```html
<div class="project-card">
    <img src="captures_prompt/power4.jpg" alt="Power4" class="project-image">
    <h3>Power4</h3>
    <p>Petit résumé rapide du projet.</p>
    <div class="project-description">
        <p>Détails: objectifs, techno, défis, résultats.</p>
    </div>
    <div class="project-tags">
        <span class="tag">Java</span>
        <span class="tag">Algorithmie</span>
    </div>
    <a href="https://github.com/sclauky/power4" class="project-link" target="_blank" rel="noopener noreferrer">Voir le projet →</a>
    <!-- Optionnel: lien live si dispo -->
    <!-- <a href="https://votre-demo.com" class="project-link" target="_blank" rel="noopener noreferrer">Live demo →</a> -->
  
</div>
```

Astuce images:
- Utilisez des images suffisamment larges (≥ 1000px) pour un rendu net.
- Le format 1:1 est parfait; sinon, le recadrage automatique garde un rendu propre.

### Contact (email, GitHub, LinkedIn)
Dans `index.html`, mettez à jour vos liens:
- Email: `mailto:mon.email@example.com`
- GitHub: `https://github.com/votre-pseudo`
- LinkedIn: `https://linkedin.com/in/votre-profil`

### CV (téléchargement)
- Le bouton CV pointe vers `cv.pdf` à la racine du projet.
- Deux options:
    1. Placer votre fichier à la racine et le nommer `cv.pdf`.
    2. Ou placer dans `cv/` et changer le lien en `cv/votre-fichier.pdf` dans `index.html`.

## 🎨 Styles clés (où les trouver)
- Variables et palette: en tête de `style.css` (`:root { ... }`).
- Grille projets: `.projects-grid` (responsive auto-fit). 
- Carte projet: `.project-card` (effet glassmorphism, hover).
- Images projet: `.project-image` (carré, non déformé, `object-fit: cover`).

## 🚀 Lancer en local

```bash
# Depuis le dossier du projet
python3 -m http.server 8000
# Ouvrez ensuite: http://localhost:8000
```

## 🌐 Déployer sur GitHub Pages
1. Créez un dépôt GitHub et poussez le code:
```bash
git init
git add .
git commit -m "Init portfolio"
git branch -M main
git remote add origin https://github.com/<votre-pseudo>/<votre-repo>.git
git push -u origin main
```
2. Dans GitHub → Settings → Pages → Source: sélectionnez la branche `main` (root).  
3. Attendez quelques minutes; votre site sera disponible à l’URL fournie par GitHub Pages.

## ❓ FAQ rapide
- `backdrop-filter` ne marche pas ? Assurez-vous d’un navigateur récent (Chrome/Firefox/Safari).
- Changer la couleur principale ? Modifiez `--color-primary` dans `:root` de `style.css`.
- Les images semblent rognées ? C’est normal: `object-fit: cover` recadre proprement pour garder un carré sans déformation.
