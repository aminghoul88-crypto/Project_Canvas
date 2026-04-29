# 🎨 DrawApp - Application de Dessin Avancée

> Une application de dessin interactive développée en HTML/CSS/JavaScript pur, fonctionnant directement dans le navigateur sans aucune installation.

---

## 📌 Description

**DrawApp** est une application web de dessin numérique qui permet à l'utilisateur de créer des illustrations librement dans son navigateur. L'application propose un pinceau personnalisable, une gomme, une palette de couleurs, un historique d'actions (undo/redo), ainsi que la possibilité d'enregistrer le dessin en PNG ou de le copier dans le presse-papier. Elle est également compatible avec les écrans tactiles (mobile/tablette).

---

## 🛠️ Technologies utilisées

| Technologie | Utilisation |
|-------------|-------------|
| **HTML5** | Structure de la page |
| **CSS3** | Mise en page, gradient, sidebar, boutons stylisés |
| **JavaScript (Vanilla)** | Logique de dessin, gestion des outils, historique |
| **Canvas API** | Rendu graphique du dessin en temps réel |
| **Touch Events API** | Support du dessin sur mobile et tablette |
| **Clipboard API** | Copie du dessin dans le presse-papier |

---

## ✨ Fonctionnalités principales

- ✏️ **Pinceau libre** — dessin à main levée avec taille ajustable (1px à 50px)
- 🧽 **Gomme** — efface des parties du dessin sans tout réinitialiser
- 🎨 **Palette de couleurs** — 8 couleurs disponibles en un clic
- ↩️ **Undo / Redo** — annuler ou rétablir les dernières actions
- 🗑️ **Effacer tout** — remet le canvas à blanc
- 💾 **Enregistrer en PNG** — télécharge le dessin comme image
- 📋 **Copier** — copie le dessin dans le presse-papier
- 📱 **Support tactile** — fonctionne sur mobile et tablette

---

## 🌐 Lien GitHub Pages

👉 [Voir le rendu final en ligne](https://aminrafrafi27-a11y.github.io/DrawApp/)

---

## 🚀 Nouveautés explorées

Durant ce projet, nous avons découvert et appris plusieurs concepts nouveaux :

- **L'API Canvas HTML5** pour dessiner en temps réel avec `lineTo`, `moveTo`, `stroke` et gérer le rendu graphique frame par frame
- **Les Touch Events** (`touchstart`, `touchmove`, `touchend`) pour adapter le dessin aux écrans tactiles mobiles
- **La Clipboard API** — une API moderne du navigateur permettant de copier une image directement dans le presse-papier via `navigator.clipboard.write()`
- **La gestion d'un historique d'états** avec `toDataURL()` et `drawImage()` pour implémenter un système undo/redo sans bibliothèque externe
- **Le redimensionnement dynamique du canvas** avec `offsetWidth` et `offsetHeight` pour s'adapter à toutes les tailles d'écran

---

## ⚠️ Difficultés rencontrées

| # | Difficulté |
|---|------------|
| 1 | Le canvas perdait tout son contenu lors du redimensionnement de la fenêtre |
| 2 | Les coordonnées touch ne correspondaient pas aux coordonnées canvas sur mobile |
| 3 | La gomme effaçait en noir au lieu d'effacer réellement le dessin |
| 4 | L'historique undo/redo consommait beaucoup de mémoire avec de nombreuses actions |
| 5 | La Clipboard API refusait de fonctionner sans contexte HTTPS sécurisé |

---

## ✅ Solutions apportées

| # | Solution |
|---|----------|
| 1 | Sauvegarde du contenu avec `toDataURL()` avant le resize et restauration avec `drawImage()` après |
| 2 | Utilisation de `getBoundingClientRect()` pour calculer l'offset exact entre la position touch et le canvas |
| 3 | Remplacement de la couleur de stroke par `#ffffff` (blanc) pour simuler l'effacement sur fond blanc |
| 4 | Limitation de l'historique en utilisant `slice()` pour ne conserver que les états nécessaires et écraser les états futurs après une nouvelle action |
| 5 | Déploiement sur GitHub Pages qui fournit automatiquement un contexte HTTPS, rendant la Clipboard API fonctionnelle |

---

## 👤 Auteur

- **aminrafrafi27-a11y**
- Projet réalisé dans le cadre d'un cours de développement web
