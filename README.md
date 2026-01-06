# Portfolio Minimaliste - Guide d'utilisation

## 📋 Vue d'ensemble
Ce portfolio vous permettra de consulter mes travaux jusqu'à aujourd'hui. En ésperant qu'il vous plaise :).

## 🗂️ Structure des fichiers

```
ia-folio/
├── index.html     # Structure HTML du site
├── style.css      # Tous les styles et effets visuels
└── README.md      # Ce fichier d'aide
```

## 🎨 Concepts CSS expliqués

### 1. **Glassmorphism** (Effet de verre)
```css
backdrop-filter: blur(10px);
background: rgba(255, 255, 255, 0.7);
```
Crée un effet de verre transparent avec flou de l'arrière-plan. Utilisé pour la navigation et les cartes.

### 2. **Variables CSS**
```css
:root {
    --color-primary: #667eea;
}
```
Permet de définir des couleurs réutilisables. Pour changer la couleur principale, modifiez `--color-primary`.

### 3. **Grid Layout**
```css
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
```
Crée une grille responsive qui s'adapte automatiquement à la taille de l'écran.

### 4. **Animations**
```css
@keyframes fadeInUp { ... }
animation: fadeInUp 1s ease-out;
```
Définit et applique des animations (apparition progressive, flottement, etc.).

## 🛠️ Comment personnaliser

### Changer les couleurs
Dans `style.css`, modifiez les variables au début :
```css
--color-primary: #votre-couleur;
--color-secondary: #votre-couleur;
```

### Modifier le contenu
Dans `index.html`, remplacez :
- Votre nom dans `<h1>`
- Les descriptions de projets
- Les liens de contact (email, GitHub, LinkedIn)

### Ajouter un projet
Copiez un bloc `.project-card` existant et modifiez son contenu.

## 🚀 Lancer le site

### Option 1 : Ouvrir directement
Double-cliquez sur `index.html` pour l'ouvrir dans votre navigateur.

### Option 2 : Serveur local (recommandé)
Pour tester avec toutes les fonctionnalités :
```bash
# Avec Python 3
python3 -m http.server 8000

# Puis ouvrir : http://localhost:8000
```

## 📱 Design Responsive
Le site s'adapte automatiquement aux mobiles, tablettes et ordinateurs grâce aux media queries et au Grid Layout.

## 🔜 Prochaines étapes possibles
- Ajouter un backend en Golang pour un formulaire de contact
- Intégrer une galerie d'images
- Ajouter un mode sombre
- Créer des animations JavaScript interactives

## 💡 Questions fréquentes

**Q: Pourquoi `backdrop-filter` ne fonctionne pas ?**  
R: Certains navigateurs anciens ne le supportent pas. Utilisez un navigateur récent (Chrome, Firefox, Safari).

**Q: Comment changer l'intensité du flou ?**  
R: Modifiez la valeur dans `blur(10px)` - un nombre plus grand = plus de flou.

**Q: Les cercles de fond sont trop visibles ?**  
R: Changez la valeur `opacity` dans `.blur-circle` (entre 0 et 1).
