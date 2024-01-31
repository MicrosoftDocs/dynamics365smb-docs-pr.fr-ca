---
author: brentholtorf
ms.topic: include
ms.date: 09/21/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

Les employés d’entrepôt peuvent livrer et recevoir des articles hors inventaire ainsi que des marchandises physiques dans les documents de vente et les bons de commande. Les articles hors inventaire sont des biens incorporels, tels que l’assurance ou les coûts supplémentaires.

Les documents de vente et les bons de commande ont souvent différents types d’éléments sur leurs lignes. Par exemple, les commandes peuvent inclure des articles du grand livre, des comptes et des immobilisations. Si vous utilisez des documents entrepôt pour gérer des articles physiques, vous pouvez également reporter certains types d’articles hors inventaire. Voici des exemples de documents entrepôt :

* Rangements inventaire
* Réceptions entrepôt
* Prélèvements inventaire
* Livraisons entrepôt

Pour permettre aux employés d'entrepôt de livrer et de recevoir des articles hors inventaire, complétez le champ **Reporter automatiquement les articles hors inventaire via l’entrepôt** sur les pages **Configuration ventes** et **Configuration achats**. Le champ fournit les options suivantes :

|Option  |Désignation  |
|---------|---------|
|Aucune     |Ne livrez ni ne recevez des articles hors inventaire.         |
|Attaché/affecté     | Reportez les frais article et autres lignes article hors inventaire qui sont attribués ou joints aux articles physiques. Pour joindre des lignes hors inventaire aux articles physiques, utilisez l’action **Joindre à la ligne inventaire**.        |
|Tout     | Reportez toutes les lignes hors inventaire dans le document source dès qu’au moins un article est reporté par le document entrepôt.        |

> [!NOTE]
> L’option **Terminé** dans le champ **Avis de livraison** du document de vente a la priorité sur la sélection dans le champ **Reporter automatiquement les articles hors inventaire via l’entrepôt** de la page **Configuration ventes**.