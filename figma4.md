---
layout: default
title: Champs, variables et calculs
permalink: /figma4/
published: true
date: 2024
---

# Variables et affichage de données

## PARTIE 1 : Réaliser une liste déroulante

### 1 - Créer un composant avec 7 variantes
![image](https://github.com/user-attachments/assets/93ea4c7f-1fbe-4aba-b051-9424f66d6fcd)

### 2 - Ajouter un changement de variante au clic pour les listes fermées
![image](https://github.com/user-attachments/assets/228c2d74-d8bc-4f42-ac75-81ff0e0fa26a)

### 3 - Créer un composant qui servira à créer l'effet visuel du survol
<p>Ce composant possède 2 états : normal et survolé. Etat normal, opacité de 0% et état survolé, opacité de 50%</p>

![image](https://github.com/user-attachments/assets/bc44c398-4821-4dd5-a8c3-2625182fc0a7)<br>

![image](https://github.com/user-attachments/assets/3cfdc528-a36d-47c9-860b-f75b68a7fca9)<br>

![image](https://github.com/user-attachments/assets/920f215a-082a-4ac0-a71d-525974400e60)

### 4 - Venir placer ce composant sur les éléments de la liste déroulée
<p>il est possible de changer l'opacité le temps de placer l'éléments</p>

![image](https://github.com/user-attachments/assets/059a8246-243f-4f08-af13-1e3b27595e77)<br>

![image](https://github.com/user-attachments/assets/6acf199f-b9e1-4b93-8841-a9ff893e5075)

### 5 - Sur chaque éléments ainsi placé, fabriquer l'interraction de retour.
![image](https://github.com/user-attachments/assets/435094d1-32d8-4425-bb6d-02658174b493)

### 6 - Tester la liste déroulante
![image](https://github.com/user-attachments/assets/979415da-1125-4174-a4dd-fedd5dbd8902)

## Partie 2 : Ajouter une variable

### 1 - Modifier une variables en fonction des choix
Ici une variable **val** sur le premier nombre (le composant au dessus)<br>
La variable s'ajoute sur l'évènement "clic" (il y a déjà une interraction au clic, on ajoute l'effet sur la variable en plus)

![image](https://github.com/user-attachments/assets/aa197a05-79f5-4bc3-927e-9f41c21bafd8)

Ajuster la valeur de la variable en fonction de la valeur cliquée (2 si on clique sur le nombre 2, 3 si on clique sur le nombre 3,...)

Attention, on ne recréé pas de variable une fois **val** créé, on modifie sa valeur.

### 2 - Afficher la variable
Pour afficher une variable, créer une zone de texte puis à droite, cliquer pour ajouter une variable
![image](https://github.com/user-attachments/assets/e27a200f-f50b-4e0b-a253-1d7421b2a847)<br>

![image](https://github.com/user-attachments/assets/b1913a73-55d9-41e7-96cf-0a79b2858137)<br>

![image](https://github.com/user-attachments/assets/e3b8a527-939a-4241-8c0a-211a72cf82b4)

### 3 - Tester la liste déroulante et l'affichage de la variable

![image](https://github.com/user-attachments/assets/5b0652dc-a31b-4db5-b78e-edd6d838c76b)


## Partie 3 : Calculs

### 1 - Mécanisme
L'objectif de cette dernière partie : insérer 2 listes déroulantes et afficher la somme des deux.
Pour cela, il faut modifier le composant. Lorsqu'une liste sera activée, il faudra faire la différence entre sa valeur d'avant et sa nouvelle valeur et **ajouter** cette différence à la somme totale.

En mathématiques, X + (-Y) équivaut à X - Y

##### Exemple 1 : 
>     
>     liste 1 : 0
>     Liste 2 : 0
>     Total : 0
>     
>Si je passe "Liste 2" à la valeur 3, la différence est de +3 (nouvelle valeur - ancienne valeur = 3 - 0 = 3)
>
>J'obtiens alors : 
>
>     liste 1 : 0
>     Liste 2 : 3
>     Total : 0 + (+3) = 3

##### Exemple 2 : 
>     
>     liste 1 : 5
>     Liste 2 : 2
>     Total : 7
>     
>Si je passe "Liste 1" à la valeur 2, la différence est de -3 (nouvelle valeur - ancienne valeur = 2 - 5 = -3)
>
>J'obtiens alors : 
>
>     liste 1 : 2
>     Liste 2 : 3
>     Total : 8 + (-3) = 5

**Mécanisme à mettre en place :** 

Lorsque je clique sur une des 2 listes fermées, je vais mémoriser dans une variable la valeur cliquée (exemple : je clique sur le bouton 3 fermé, je mémorise 3)<br>
![image](https://github.com/user-attachments/assets/ca8b9b4c-da53-40a5-b11f-5e15f1d34934)<br>

![image](https://github.com/user-attachments/assets/4d4b4300-93c2-4be8-9436-adcd64b9d282)

Lorsque je clique sur une valeur dans la liste ouverte, j'utilise la valeur mémorisée précédemment pour calculer la différence.<br>
Je profite de ce calcul pour mettre à jour la variable qui calcul la somme<br> 
Avant :<br>
![image](https://github.com/user-attachments/assets/16bbb44f-948e-4070-8feb-d3839eaa0d82)<br>
Après : <br>
![image](https://github.com/user-attachments/assets/af84a4c6-867d-4b74-a743-93cfe9826366)

### 2 - Tester
![image](https://github.com/user-attachments/assets/88c14f1a-12d5-4af1-a4c5-37236a00c695)

