---
title: "Procédure : créer des séries de numéros | Microsoft Docs"
description: "Découvrez comment configurer des séries de numéros qui affectent les codes d'identification uniques aux comptes et aux documents dans Dynamics 365 for Financials."
documentationcenter: 
author: SusanneWindfeldPedersen
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: numbers, numbering
ms.date: 06/02/2017
ms.author: solsen
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 7cc119c5879400adf63e468259a2c3a275b71cca
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---
# <a name="how-to-create-number-series"></a>Procédure : créer des séries de numéros
Pour chaque compagnie que vous configurez, vous devez affecter des codes d'identification uniques aux éléments tels que les comptes du grand livre, les comptes client et fournisseur, les factures et d'autres documents. La numérotation est importante, pas uniquement pour l'identification. Un système de numérotation bien conçu facilite également la gestion et l'analyse de la compagnie et permet de réduire les erreurs de saisie des données.

> [!NOTE]  
>   Il est recommandé d'utiliser les mêmes codes souche de numéros que ceux répertoriés dans la fenêtre **Liste de souches de numéros** de la société de démonstration CRONUS. Des codes tels que *P-INV+* ne vont pas vous paraître significatifs au premier abord, mais [!INCLUDE[d365fin](includes/d365fin_md.md)] dispose d'un certain nombre de paramètres par défaut en fonction de ces codes souche de numéros.

Vous créez un système de numérotation en définissant un ou plusieurs codes pour chaque type de données de base ou de document. Par exemple, vous pouvez définir un code pour la numérotation de clients, un code pour la numérotation des factures vente et un autre code pour la numérotation des documents dans les feuilles comptabilité. Une fois que vous avez défini un code, vous devez définir au moins une ligne série de numéros. Celle-ci contient des informations telles que les premier et dernier numéros de la série et la date début. Vous pouvez définir plusieurs lignes série de numéros par code série de numéros, avec une date début différente pour chaque ligne. Les séries sont utilisées de manière consécutive, chaque série commençant à la date début respective.

Vous devez généralement définir votre série de numéros pour insérer automatiquement le numéro suivant sur des fiches ou des documents que vous créez. Toutefois, vous pouvez également définir une série de numéros pour permettre la saisie manuelle du nouveau numéro. Vous devez spécifiez cela dans **N° manuels** .

Si vous voulez utiliser plusieurs codes série de numéros pour un type de données de base (par exemple, si vous voulez utiliser différentes séries de numéros pour diverses catégories d'articles), vous pouvez utiliser des liens de séries de numéros.

## <a name="to-create-a-new-number-series"></a>Pour créer des séries de numéros
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône"), entrez **Souches de n°**, puis sélectionnez le lien connexe.
2. Sélectionnez l'action **Nouveau**.
3. Sur la nouvelle ligne, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

**ASTUCE** : pour permettre la saisie manuelle d'un numéro sur de nouvelles fiches ou de nouveaux documents, désélectionnez **N° par défaut** et sélectionnez **N° manuels** .

Désormais, lorsque vous créez une fiche ou un document configuré pour utiliser la souche de numéros en question, vous pouvez renseigner manuellement le champ **N°** avec n'importe quelle valeur.  

## <a name="to-set-up-where-a-number-series-is-used"></a>Pour définir l'emplacement d'utilisation de la série de numéros
La procédure suivante indique comment définir des séries de numéros pour la zone Ventes. La procédure est identique pour d'autres secteurs.
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône"), entrez **Souches de n°**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Ventes**, dans le raccourci **Souche de numéros**, sélectionnez la souche de numéros souhaitée pour chaque fiche ou document vente.

Le numéro sélectionné est désormais utilisé pour renseigner le champ **N°** sur la fiche ou le document en question, en fonction des paramètres définis sur la ligne série de numéros.

## <a name="to-create-relationships-between-number-series"></a>Pour créer des liens entre des séries de numéros
Si vous avez défini plusieurs codes série de numéros pour un même type d'informations ou de transactions de base, vous pouvez créer des liens entre ces codes. Cette fonction peut vous aider à choisir parmi ces codes lorsque vous utilisez un numéro.

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône"), entrez **Souches de n°**, puis sélectionnez le lien connexe.
2. Sélectionnez la ligne avec la souche de numéros pour laquelle vous souhaitez créer des relations, puis cliquez sur **Relations**.
3. Dans le champ **Code souche**, entrez le code de la souche de numéros à lier à la souche sélectionnée à l'étape 2.
4. Ajoutez une ligne pour chaque code à lier à la série de numéros sélectionnée.
5. Fermez la fenêtre.

Désormais, pour créer un élément nécessitant un numéro, vous pourrez utiliser les liens ainsi créés et choisir parmi les séries de numéros liées.

## <a name="see-also"></a>Voir aussi
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

