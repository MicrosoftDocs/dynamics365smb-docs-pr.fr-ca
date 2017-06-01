---
title: "Procédure : traiter les retours ou annulations d&quot;achats| Microsoft Docs"
description: "Procédure : traiter les retours ou annulations d&quot;achats"
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cancel, undo, correct
ms.date: 03/29/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: f87b51ac746c6586e4ebb3b09aaa8d5ee7ac391d
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="how-to-process-purchase-returns-or-cancellations"></a>Procédure : traiter les retours ou annulations d'achats
Si vous souhaitez retourner des articles à votre fournisseur ou annuler des services que vous avez achetés, vous pouvez créer et reporter une note de crédit achat qui indique la modification demandée par rapport à la facture achat d'origine. Pour inclure les informations de facture achat correctes, vous pouvez créer la note de crédit achat à partir de la facture achat reportée ou utiliser la fonction de copie.

**Remarque** : si une facture achat validée n'a pas encore été payée, vous pouvez utiliser les fonctions **Corriger** ou **Annuler** sur la facture achat validée pour contrepasser automatiquement les transactions concernées. Ces fonctions ne fonctionnent que pour les factures impayées, elles ne prennent pas en charge des retours partiels ou les annulations. Pour plus d'informations, reportez-vous à [Procédure : corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

Généralement, vous créez une note de crédit achat en réaction à une note de crédit qu'un fournisseur vous a envoyée. La note de crédit achat fonctionne comme votre documentation interne du processus de note de crédit à des fins comptables.

La modification peut concerner tous les produits figurant sur la facture achat d'origine, ou uniquement certains d'entre eux. Par conséquent, vous pouvez partiellement renvoyer les articles reçus ou demander le remboursement partiel des services reçus. Dans ce cas, vous devez modifier les informations de facture achat copiées.

Outre la facture achat reportée d'origine, vous pouvez affecter la note de crédit achat à d'autres documents achat, par exemple une autre facture achat reportée, parce que vous renvoyez également des articles livrés avec cette facture.

## <a name="to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice"></a>Pour créer une note de crédit achat à partir d'une facture achat reportée
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Avoirs achat**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Factures achat enregistrées**, sélectionnez la facture achat validée que vous souhaitez contrepasser, puis sélectionnez l'action **Créer un avoir correctif**.

    La plupart des champs de l'en-tête de la note de crédit achat sont renseignés avec les informations de la facture achat reportée. Vous pouvez modifier tous les champs, par exemple avec de nouvelles informations qui reflètent l'entente de retour.
3. Modifiez les informations des lignes en fonction de l'entente, par exemple le nombre d'articles retournés ou le montant à rembourser.
4. Sélectionnez l'action **Lettrer écritures**.
5. Dans la fenêtre **Lettrer écritures fournisseur**, sélectionnez la ligne contenant le document achat validé auquel vous souhaitez lettrer l'avoir achat, puis sélectionnez l'action **ID lettrage**. Le numéro de l'avoir achat est inséré dans le champ **ID lettrage**.
6. Dans le champ **Montant à lettrer**, entrez le montant à lettrer s'il est inférieur au montant initial.

    Au bas de la fenêtre **Lettrer écritures fournisseur**, vous pouvez afficher le montant total à lettrer pour contrepasser toutes les écritures concernées, à savoir lorsque la valeur du champ **Solde** est égale à zéro.
7. Cliquez sur le bouton **OK**. Lorsque vous reportez la note de crédit achat, elle est affectée aux documents achat reportés spécifiés.

    Lorsque vous avez créé ou modifié les lignes note de crédit achat nécessaires et qu'une ou plusieurs applications sont spécifiées, vous pouvez procéder au report de la note de crédit achat.
8. Sélectionnez l'action **Valider**.

Les factures achat reportées auxquelles vous affectez la note de crédit sont à présent inversées. Si vous avez déjà payé la facture initiale, le fournisseur doit maintenant rembourser le paiement en votre faveur. Si la note de crédit est uniquement pour une partie du produit dans la facture initiale, vous pouvez payer uniquement le montant restant de la facture achat d'origine pour la fermer.

La note de crédit achat est supprimée et remplacée par un nouveau document dans la liste des notes de crédit achat reportées.

## <a name="to-create-a-purchase-credit-memo-from-scratch"></a>Pour créer une note de crédit achat à partir de zéro
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Factures achat enregistrées**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau** pour ouvrir un nouvel avoir achat vierge.
3. Dans le champ **Fournisseur**, entrez le nom d'un fournisseur existant.
4. Sélectionnez l'action **Copier document**.
5. Dans la fenêtre **Extraire document achat**, dans le champ **Type document**, sélectionnez **Facture enregistrée**.
6. Sélectionnez le champ **N° document** pour ouvrir la fenêtre **Factures achat enregistrées**, puis sélectionnez la facture achat validée qui contient les lignes que vous souhaitez contrepasser.
7. Activez la case à cocher **Recalculer lignes** si vous souhaitez que les lignes facture achat validées copiées soient mises à jour avec les modifications apportées au prix article et au coût unitaire depuis la validation de la facture.
8. Cliquez sur le bouton **OK**. Les lignes facture copiées sont insérées dans la note de crédit achat.
9. Remplissez la note de crédit achat en vous reportant à la section « Pour créer une note de crédit achat à partir d'une facture achat reportée » de cette rubrique.

## <a name="see-also"></a>Voir aussi
[Achats](purchasing-manage-purchasing.md)  
[Procédure : enregistrer des achats](purchasing-how-record-purchases.md)  
[Procédure : corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

