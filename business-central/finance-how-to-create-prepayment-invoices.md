---
title: 'Procédure : créer des factures de paiement anticipé | Microsoft Docs'
description: Découvrez comment gérer les situations où votre fournisseur ou vous-même exigez un paiement anticipé.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: 96433274efa8ea8f5ec93248f4a7c992e456aa26
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "912251"
---
# <a name="create-prepayment-invoices"></a>Créer des factures de paiement anticipé
Si vous voulez que vos clients fassent des paiements avant de leur livrer une commande ou si votre fournisseur exige que vous fassiez un paiement avant de vous livrer une commande, vous pouvez utiliser la fonctionnalité Paiement anticipé.  

Après avoir créé un document de vente ou un bon de commande, vous pouvez créer une facture paiement anticipé. Vous pouvez utiliser les pourcentages par défaut pour chaque ligne vente ou achat, ou ajuster le montant en fonction si nécessaire. Par exemple, vous pouvez spécifier un montant total pour la commande entière.  

La procédure suivante décrit comment facturer un paiement anticipé pour des documents de vente. La procédure est identique pour les bons de commande.  

## <a name="to-create-a-prepayment-invoice"></a>Pour créer une facture paiement anticipé  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents de vente**, puis sélectionnez le lien associé.  
2. Créez un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  

    Sur le raccourci **Acompte** le champ **% acompte** est renseigné automatiquement si un pourcentage d'acompte par défaut figure sur la fiche client. Vous pouvez modifier le contenu du champ. Le pourcentage de paiement anticipé est uniquement copié à partir de l'en-tête vers les lignes qui ne copient pas le pourcentage de paiement anticipé par défaut à partir de l'article.  

    La sélection du champ **Compresser acompte** signifie que les lignes sont combinées sur la facture si :  
    - Elles ont le même compte du grand livre pour les paiements anticipés,comme déterminé par la configuration de report générale.  
    - Elles sont les mêmes dimensions.  

    Laissez le champ vide si vous souhaitez spécifier une facture paiement anticipé avec une ligne pour chaque ligne document de vente à laquelle un pourcentage de paiement anticipé est associé.  

3. Renseignez les lignes vente.  

    Si des pourcentages d'acompte par défaut ont été configurés pour vos articles, ils sont copiés automatiquement dans le champ **% acompte** sur la ligne. Sinon, le pourcentage de paiement anticipé est copié à partir de l'en-tête. Vous pouvez modifier le contenu du champ **% acompte** sur la ligne.  
4. Si vous voulez appliquer un pourcentage d'acompte à la commande entière, modifiez le champ **% acompte** dans l'en\-tête après avoir renseigné les lignes.  
5. Pour visualiser le montant du paiement anticipé total, choisissez l'action **Statistiques**.

    Pour ajuster le montant de paiement anticipé total de la commande, vous pouvez modifier le contenu du champ **Montant paiement anticipé** de la page **Statistiques document de vente**.  

    Si le champ **Prix TVA comprise** est sélectionné, le champ **Montant acompte TTC** est modifiable.  

    Si vous modifiez la valeur du champ **Montant acompte**, le montant est réparti de façon proportionnelle entre toutes les lignes, à l'exception de celles qui contiennent la valeur **0** dans le champ **% acompte**.  
6. Pour effectuer un rapport de test avant de reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis choisissez **Rapport de test de paiement anticipé**.  
7. Pour reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis l'action **Reporter facture paiement anticipé**.  

    Pour reporter et imprimer la facture paiement anticipé, choisissez l'action **Reporter et imprimer facture paiement anticipé**.  

Vous pouvez émettre des factures paiement anticipé supplémentaires pour la commande. Pour ce faire, augmentez le montant du paiement anticipé sur une ou plusieurs lignes, ajustez la date document si nécessaire, puis reportez la facture paiement anticipé. Une nouvelle facture est créée pour la différence entre les montants de paiement anticipé facturés jusqu'ici et le nouveau montant de paiement anticipé.  

> [!NOTE]  
>  Si vous êtes situé en Amérique du Nord, vous ne pouvez pas modifier le pourcentage de paiement anticipé après la facture paiement anticipé reportée. Cela est empêché dans la version nord\-américaine de [!INCLUDE[d365fin](includes/d365fin_md.md)], car le calcul de la taxe sur les ventes est sinon incorrect.  

 Lorsque vous êtes prêt à reporter le reste de la facture, reportez-le comme n'importe quelle facture. Le montant du paiement anticipé est automatiquement déduit du montant dû.  

## <a name="see-also"></a>Voir aussi  
[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Procédure pas à pas : configuration et facturation d'acomptes](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
