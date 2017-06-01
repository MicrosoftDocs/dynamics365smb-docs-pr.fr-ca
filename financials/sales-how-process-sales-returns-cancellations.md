---
title: "Procédure : traiter les retours ou annulations de ventes| Microsoft Docs"
description: "Procédure : traiter les retours ou annulations de ventes"
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 03/29/2016
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: cf471e0c3a13a954ab7604a8b1d0f715f664722d
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="how-to-process-sales-returns-or-cancellations"></a>Procédure : traiter les retours ou annulations de ventes
Si vous avez vendu des articles ou services à un client pour lesquels vous avez reçu un paiement et que le client souhaite retourner les articles ou annuler les services, vous devez créer et reporter une note de crédit vente qui indique la modification demandée. Pour inclure les informations de facture vente correctes, vous pouvez créer la note de crédit vente à partir de la facture vente reportée ou utiliser la fonction de copie.  

**Remarque** : si une facture vente validée n'a pas encore été payée, vous pouvez utiliser les fonctions **Corriger** ou **Annuler** sur la facture vente validée pour contrepasser automatiquement les transactions associées. Ces fonctions ne fonctionnent que pour les factures impayées, elles ne prennent pas en charge des retours partiels ou les annulations. Pour plus d'informations, reportez-vous à [Procédure : corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md).

Outre la facture vente reportée d'origine, vous pouvez affecter la note de crédit vente à d'autres documents vente, par exemple une autre facture vente reportée, parce que le client renvoie également des articles livrés avec cette facture.

Un retour ou un remboursement peut en effet se rapporter uniquement à certains des articles ou des services figurant sur la facture vente initiale. Dans ce cas, vous devez modifier les informations sur les lignes de la note de crédit vente. Lors du report de la note de crédit vente, les documents vente affectés par la modification sont inversés et un paiement de remboursement peut être créé pour le client.  

Vous pouvez envoyer la note de crédit vente reportée au client pour confirmer le retour ou l'annulation et communiquer que la valeur associée sera remboursée, par exemple lorsque les articles sont renvoyés.  

## <a name="to-create-a-sales-credit-memo-from-a-posted-sales-invoice"></a>Pour créer une note de crédit vente à partir d'une facture vente reportée
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Factures vente enregistrées**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Factures vente enregistrées**, sélectionnez la facture vente validée que vous souhaitez contrepasser, puis sélectionnez l'action **Créer un avoir correctif**.

    L'en-tête de la note de crédit vente affiche des informations sur la facture vente reportée. Vous pouvez les modifier, par exemple avec de nouvelles informations qui reflètent l'entente de retour.  
3. Modifiez les informations des lignes en fonction de l'entente, par exemple le nombre d'articles retournés ou le montant à rembourser.
4. Sélectionnez l'action **Lettrer écritures**.
5. Dans la fenêtre **Lettrer écritures client**, sélectionnez la ligne contenant le document vente validé auquel vous souhaitez lettrer l'avoir vente, puis sélectionnez l'action **ID lettrage**.

    L'identifiant de l'avoir vente s'affiche dans le champ **ID lettrage**.
6. Dans le champ **Montant à lettrer**, entrez le montant à lettrer s'il est inférieur au montant initial.  

    Au bas de la fenêtre **Lettrer écritures client**, vous pouvez afficher le montant total à lettrer pour contrepasser toutes les écritures concernées, à savoir lorsque la valeur du champ **Solde** est égale à zéro.
7. Cliquez sur le bouton **OK**. Lors du report de la note de crédit vente, elle est affectée aux documents vente reportés.

    Après que vous avez créé ou modifié les lignes note de crédit vente et spécifié une ou plusieurs applications, vous pouvez procéder au report de la note de crédit vente.   
8. Sélectionnez l'action **Valider et envoyer**.  

La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode d'envoi par défaut du client. Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**. Pour plus d'informations, reportez vous à [Procédure : configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).  

Les documents vente reportés auxquels vous avez affecté la note de crédit sont à présent inversés, et un remboursement peut être créé pour le client. La note de crédit vente est supprimée et remplacée par un nouveau document dans la liste des notes de crédit vente reportées.

## <a name="to-create-a-sales-credit-memo-from-scratch"></a>Pour créer une note de crédit vente à partir de zéro
1. Dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Factures vente enregistrées**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau** pour ouvrir un nouvel avoir vente vierge.
3. Dans le champ **Client**, entrez le nom d'un client existant.
4. Sélectionnez l'action **Copier document**.
5. Dans la fenêtre **Extraire document vente**, dans le champ **Type document**, sélectionnez **Facture enregistrée**.
6. Sélectionnez le champ **N° document** pour ouvrir la fenêtre **Factures vente enregistrées**, puis sélectionnez la facture vente validée qui contient les lignes que vous souhaitez contrepasser.
7. Activez la case à cocher **Recalculer lignes** si vous souhaitez que les lignes facture vente validées copiées soient mises à jour avec les modifications apportées au prix article et au coût unitaire depuis la validation de la facture.
8. Cliquez sur le bouton **OK**. Les lignes facture copiées sont insérées dans la note de crédit vente.
9. Remplissez la note de crédit vente en vous reportant à la section « Pour créer une note de crédit vente à partir d'une facture vente reportée » de cette rubrique.

## <a name="see-also"></a>Voir aussi
[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Procédure : envoyer des documents par e-mail](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

