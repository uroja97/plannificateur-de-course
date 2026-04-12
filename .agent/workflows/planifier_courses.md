---
description: Planifier un menu anti-inflammatoire de 2 semaines et générer la liste de courses chez Costco
---

# Workflow : Planificateur de courses anti-inflammatoire

Ce workflow a pour but de générer un planning de repas et une liste de courses associée pour 2 semaines, adaptés à une famille de 4 personnes (2 adultes, 2 enfants), avec un budget d'environ 400$, principalement chez Costco, en suivant un régime anti-inflammatoire.

## Étape 1 : Inventaire rapide
Demandez à l'utilisateur :
- S'il y a des ingrédients d'une précédente semaine qu'il faut absolument utiliser (restes, produits au congélateur ou dans le garde-manger).
- S'il y a des événements particuliers prévus dans les deux prochaines semaines (ex: repas à l'extérieur, invités).

## Étape 2 : Proposition du Menu (2 semaines)
Générez un tableau ou une liste de repas pour 14 jours incluant :
- Le déjeuner (matin)
- Le dîner (midi)
- La collation
- Le souper (soir)
*Assurez-vous de vous appuyer sur les directives figurant dans la compétence `planificateur_anti_inflammatoire`.*

## Étape 3 : Ajustement et Validation
Présentez le menu à l'utilisateur et demandez-lui son avis.
Effectuez les modifications demandées jusqu'à ce que le menu soit validé.

## Étape 4 : Fiches de Préparation Détaillées (Jour par Jour)
Après validation du menu, générez un fichier de fiches jour par jour au format "Todo List" sympathique. Pour chaque jour, détaillez :
- Les ingrédients nécessaires (avec des cases à cocher `[ ]`).
- Les recettes précises pour chaque repas (Déjeuner, Dîner, Collation, Souper).
- Les consignes de préparation claires, en mettant en évidence le *batch-cooking* et l'organisation du temps.

## Étape 5 : Génération de la Liste de Courses
Une fois les fiches créées, extrayez une liste de courses exhaustive.
- Regroupez les articles par rayon (ex: Fruits et Légumes, Viande/Poisson, Frais/Laitier, Surgelés, Épicerie/Garde-manger).
- Privilégiez l'estimation de quantités au format familial (produits type Costco).
- **Format Strict :** Un seul type d'article par ligne dans la liste à cocher. Ne regroupez jamais les articles avec des `/` (ex: séparer "Pommes / Poires" en deux lignes distinctes).
- **Obligatoire :** Demandez toujours à l'utilisateur s'il a besoin d'ajouter des produits d'entretien ou pour la maison (ex: lessive, papier toilette, etc.) à sa liste globale.
- Estimez le coût pour vérifier s'il s'approche du budget cible de 400$.

## Étape 6 : Sauvegarde des fichiers
Créez ou mettez à jour les fichiers suivants de manière autonome :
1. Créez un fichier d'historique dans le répertoire `historique_plannings/` (ex: `historique_plannings/planning_2026-04-11.md`) contenant le menu validé, les fiches jour par jour, et la liste de courses.
2. Demandez à l'utilisateur de bien vouloir faire ses courses puis de partager la photo/scan de son ticket de caisse.

## Étape 7 : Analyse du ticket de caisse (Au retour des courses)
*Cette étape se déclenche quand l'utilisateur fournit une image de ticket de caisse.*
1. Lisez le ticket de caisse fourni.
2. Comparez le total réel avec l'estimation et le budget de 400$.
3. Extrayez les produits récurrents pour alimenter/modifier le fichier `base_de_donnees/produits_frequents_costco.md`.
4. Ajoutez un résumé de cette dépense dans le fichier d'historique de la session correspondante.
