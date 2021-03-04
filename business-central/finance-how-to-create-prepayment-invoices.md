---
title: 'Procédure : créer des factures de paiement anticipé | Microsoft Docs'
description: Découvrez comment gérer les situations où votre fournisseur ou vous-même exigez un paiement anticipé.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 5f227cc73531111ae15f69d6fba5ac541e28560c
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4746876"
---
# <a name="create-prepayment-invoices"></a>Créer des factures de paiement anticipé

Si vous demandez à vos clients de soumettre le paiement avant de leur livrer une commande, vous pouvez utiliser la fonctionnalité de paiement anticipé. Il en va de même si votre fournisseur vous demande de soumettre un paiement avant de vous livrer une commande.  

Vous pouvez lancer le traitement du paiement anticipé lorsque vous créez un document vente ou un bon de commande. Si vous avez un pourcentage paiement anticipé par défaut pour ce client ou fournisseur, celui-ci sera automatiquement inclus dans la facture paiement anticipé résultante. Vous pouvez également spécifier un pourcentage paiement anticipé pour l'ensemble du document.

Après avoir créé un document de vente ou un bon de commande, vous pouvez créer une facture paiement anticipé. Vous pouvez utiliser les pourcentages par défaut pour chaque ligne vente ou achat, ou ajuster le montant en fonction si nécessaire. Par exemple, vous pouvez spécifier un montant total pour la commande entière.  

La procédure suivante décrit comment facturer un paiement anticipé pour un document de vente. La procédure est identique pour les bons de commande.  

## <a name="to-create-a-prepayment-invoice"></a>Pour créer une facture paiement anticipé

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Créez un document de vente pour le client approprié. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  

    Sur le raccourci **Paiement anticipé**, le champ **% paiement anticipé** spécifie le pourcentage à utiliser pour calculer le montant paiement anticipé. Si un pourcentage de paiement anticipé par défaut figure sur la fiche client, le champ est renseigné automatiquement. Vous pouvez modifier le pourcentage. <!--This percentage is applied to lines where the item on that line does not already specify a prepayment percentage. The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.-->  

    Choisissez le champ **Compresser paiement anticipé** si vous souhaitez créer des lignes sur la facture de paiement anticipé qui combinent des lignes du document de vente si :  

    - Elles ont le même compte du grand livre pour les paiements anticipés,comme déterminé par la configuration de report générale.  
    - Elles sont les mêmes dimensions.  

    Si vous souhaitez spécifier une facture paiement anticipé avec une ligne pour chaque ligne document de vente à laquelle un pourcentage de paiement anticipé est associé, alors ne choisissez pas le champ **Compresser paiement anticipé**.  

    La date d'échéance du paiement anticipé est calculée automatiquement en fonction de la valeur du **Code modalités de paiement anticipé**.

3. Renseignez les lignes vente.  

    Si vous avez spécifié un pourcentage paiement anticipé par défaut soit pour le client, soit sur le raccourci **Paiement anticipé** sur ce document, cette valeur est copiée sur chaque ligne. Vous pouvez modifier le contenu du champ **% acompte** sur la ligne.  

4. Pour visualiser le montant du paiement anticipé total, choisissez l'action **Statistiques**.

    Pour ajuster le montant de paiement anticipé total de la commande, vous pouvez modifier le contenu du champ **Montant paiement anticipé** de la page **Statistiques document de vente**.  

    Si le champ **Prix TVA comprise** est sélectionné, le champ **Montant acompte TTC** est modifiable.  

    Si vous modifiez la valeur du champ **Montant acompte**, le montant est réparti de façon proportionnelle entre toutes les lignes, à l'exception de celles qui contiennent la valeur **0** dans le champ **% acompte**.  

5. Pour effectuer un rapport de test avant de reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis choisissez **Rapport de test de paiement anticipé**.  
6. Pour reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis l'action **Reporter facture paiement anticipé**.  

    Pour reporter et imprimer la facture paiement anticipé, choisissez l'action **Reporter et imprimer facture paiement anticipé**.  

Vous pouvez émettre des factures paiement anticipé supplémentaires pour la commande. Pour ce faire, augmentez le montant du paiement anticipé sur une ou plusieurs lignes, ajustez la date document si nécessaire, puis reportez la facture paiement anticipé. Une nouvelle facture est créée pour la différence entre les montants de paiement anticipé facturés jusqu'ici et le nouveau montant de paiement anticipé.  

> [!NOTE]  
> Si vous êtes situé en Amérique du Nord, vous ne pouvez pas modifier le pourcentage de paiement anticipé après la facture paiement anticipé reportée. Cela est empêché dans la version nord\-américaine de [!INCLUDE[prod_short](includes/prod_short.md)], car le calcul de la taxe sur les ventes est sinon incorrect.  

 Lorsque vous êtes prêt à reporter le reste de la facture, reportez-le comme n'importe quelle facture. Le montant du paiement anticipé est automatiquement déduit du montant dû.  

## <a name="see-also"></a>Voir aussi

[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Procédure pas à pas : Configuration et facturation de paiements anticipés](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]