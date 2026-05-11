---
description: Planifier un menu anti-inflammatoire de 2 semaines et générer la liste de courses chez Costco
---

# Workflow : Planificateur de courses anti-inflammatoire

Ce workflow a pour but de générer un planning de repas et une liste de courses associée pour 2 semaines, adaptés à une famille de 4 personnes (2 adultes, 2 enfants), avec un budget d'environ 400$, principalement chez Costco, en suivant un régime anti-inflammatoire.

## Étape 1 : Inventaire rapide et Déduction Automatique
1. **Analyse de l'historique** : Lisez le dernier planning généré. En fonction de sa date (ex: il y a 15 jours) et des grammages initiaux, déduisez ce qui devrait logiquement rester. Considérez par défaut que les produits frais (fruits, légumes, laitiers) et viandes non congelées sont terminés.
2. Demandez à l'utilisateur :
   - De confirmer vos déductions sur le garde-manger (pâtes, conserves) et le congélateur.
   - S'il y a des événements particuliers prévus dans les deux prochaines semaines (ex: repas à l'extérieur, invités).

## Étape 2 : Génération du Menu, des Fiches Détaillées et de la Liste de Courses
Dès la première proposition, vous devez générer et fournir le planning COMPLET, qui inclut :
1. **Un tableau récapitulatif** du menu pour 14 jours (Déjeuner, Dîner, Collation, Souper).
2. **Les fiches de préparation détaillées** pour chaque jour. **Il est obligatoire d'utiliser le format strict suivant :**
   - **Ingrédients du jour** : Commencer par `**[ ] Ingrédients du jour :**` suivi d'une liste à puces (`*`) avec la **quantité exacte** pour 4 personnes.
   - **Recettes et Préparation** : Indiquez le plat en gras, suivi d'une sous-puce `- *Préparation :*` avec les instructions pas-à-pas.
   - **Batch-cooking** : Terminer par une puce `- **💡 Batch Cooking :**`.
3. **La liste de courses exhaustive**, regroupée par rayon, avec des quantités et formats précis (type Costco). Demandez toujours à l'utilisateur s'il a besoin de produits d'entretien. Estimez le coût.

*Assurez-vous de vous appuyer sur les directives figurant dans la compétence `planificateur_anti_inflammatoire`.*

## Étape 3 : Sauvegarde et Validation
1. Créez ou mettez à jour un fichier d'historique dans le répertoire `historique_plannings/` (ex: `historique_plannings/planning_2026-04-11.md`) contenant TOUT : le menu, les fiches détaillées, et la liste de courses.
2. Présentez le tout à l'utilisateur et demandez-lui de valider ou de demander des ajustements.
3. Rappelez-lui de partager la photo/scan de son ticket de caisse après ses courses.

## Étape 7 : Analyse du ticket de caisse (Au retour des courses)
*Cette étape se déclenche quand l'utilisateur fournit une image de ticket de caisse.*
1. Lisez le ticket de caisse fourni.
2. Comparez le total réel avec l'estimation et le budget de 400$.
3. Extrayez les produits récurrents pour alimenter/modifier le fichier `base_de_donnees/produits_frequents_costco.md`.
4. Ajoutez un résumé de cette dépense dans le fichier d'historique de la session correspondante.
