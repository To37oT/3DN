---
layout: default
title: Figma - De la maquette au navigateur
permalink: /figma-tp0/
published: true
date: 2026
---
 
# TP0 - De la maquette au navigateur (4h)
 
> Objectif : réactiver les compétences de 2ème année (conception, intégration) et découvrir l'exportation des ressources.
>
> Fil conducteur : une mini page (header + rangée de cartes produit).
 
## Bloc 1 — Réactivation Figma (~1h00)
 
🔎 **Rappels**
- Une **frame** structure le design ; une **grille** (layout grid) guide les alignements.
- Un **composant** est un élément réutilisable : ses instances se mettent à jour automatiquement.
- L'**auto layout** gère la disposition automatique : padding, gap, comportements hug/fill.

✏ **Construire la page** 
- Créer un fichier `tp0-nom-prenom` dans votre équipe.
- Créer une frame **Desktop 1280**, avec une grille de **12 colonnes, largeur 80, gouttière 20, centrée**.
- Construire une **carte produit** en **auto layout** : image (placeholder), titre, texte court, bouton.
>Pour rappel, voici la création d'un bouton en auto layout `Maj + A` :
>- Créer d'abord le texte « Ajouter au panier »
>- Le sélectionner, puis `Maj + A` : Figma l'enveloppe automatiquement dans un cadre auto layout
>- Dans le panneau `auto layout` de droite : règler le padding, donner un fill de couleur au cadre, un corner radius,...
>- Le bouton s'adapte désormais à son texte.
- Transformer la carte en **composant** (clic droit), placer **3 instances** en rangée (⚠️placer le composant maitre dans une page dédiée), alignées sur la grille.
- Ajouter un **header** : nom de marque (texte) + navigation (3 liens).
- ⚠️ Nommer chaque élément **à sa création** (conventions habituelles : `encart-produit`, `btn-ajouter`...).

## Bloc 2 — Réflexion responsive (~30 min)
 
🔎 **Que devient la page sur mobile ?**
- Les tailles d'écran imposent d'adapter la mise en page : c'est le **responsive design**.
- Un **breakpoint** est un seuil de largeur où la mise en page change.
- En CSS, ce sont les **media queries** qui appliquent ces changements (bloc 4).

✏ **Décliner la maquette**
- Dupliquer la frame et la redimensionner en **375px** de large.
- Réarranger : la rangée de cartes **s'empile**, la navigation se simplifie.
- Observer : grâce à l'auto layout, l'adaptation est presque automatique — c'est tout son intérêt.

## Bloc 3 — Exporter depuis Figma (~30 min) 🆕
🔎 **Formats d'export natif dans figma**
 
- **JPG** : photos (léger, pas de transparence).
- **PNG** : transparence nécessaire (attention au poids).
- **SVG** : logos, icônes, formes vectorielles (redimensionnable sans perte).
- Les multiplicateurs **@1x / @2x** servent les écrans haute densité (Retina).

> Afin d'optimiser nos images, il faudra les convertir si nécessaire en WebP, Avif,... pour cela nous pouvons soit utiliser un plugin, soit photoshop après l'export, soit le site web squoosh.app (google) également après l'export. 

✏ **Exporter les ressources** 
- Sélectionner l'image d'une carte → panneau **Export** → choisir le format adapté → **Export**.
- ⚠️ Piège classique : exporter l'image *seule*, pas son conteneur (le cadrage peut alors changer).
- Nommer les fichiers de manière normée : `img-produit-01.jpg`, `logo.svg`…
- Ranger tous les exports dans un dossier `img/`.
  
✏ **Relever les valeurs**
- Noter les **couleurs** (code hex), les **typographies** (nom, taille, graisse) et les **espacements** de votre maquette.
- Astuce : clic droit → *Copy as code → CSS*, ou **Dev Mode** (`Maj + D`) → onglet Code.
- ⚠️ Le code généré fournit des **valeurs** fiables, pas une logique CSS propre : on s'en sert comme relevé, pas comme code final.

## Bloc 4 — Intégration web (~2h00)
✏ **Préparer l'environnement**
 
- Créer un dossier `tp0` contenant : `index.html`, `style.css`, et votre dossier `img/`.
- ⚠️ Les chemins vers les images sont **relatifs** : `img/img-produit-01.jpg`. Une image cassée = un chemin à vérifier.
  
✏ **Structure HTML**
- Un `<header>` : nom de marque + navigation.
- Un `<main>` avec les 3 cartes — même structure HTML répétée : c'est l'équivalent code de votre composant Figma.
  
✏ **CSS**
- Reprendre les **valeurs relevées** au bloc 3 (couleurs, typos, espacements).
- La rangée de cartes en **flexbox** — le parallèle avec l'auto layout : `flex-direction` ≈ direction, `gap` ≈ gap, `padding` ≈ padding.
- Le bouton : `cursor: pointer;` et un effet de survol :
```css
.btn-principal {
  transition: background-color 0.2s ease-out;
}
.btn-principal:hover {
  background-color: /* votre couleur hover */;
}
```
 
✏ **Responsive**
- Une media query pour retrouver votre maquette mobile :
```css
@media (max-width: 768px) {
  .rangee-cartes {
    flex-direction: column;
  }
}
```
- Tester en réduisant la fenêtre du navigateur (ou `F12` → mode responsive).
- 
## Rendu
- Maquette Figma partagée en lien éditable — vérification croisée avec un camarade conseillée.
- Dossier d'intégration complet (`index.html`, `style.css`, `img/`) compressé et déposé sur itslearning.
- Un point d'historique `rendu-tp` créé dans Figma avant le partage.
 




