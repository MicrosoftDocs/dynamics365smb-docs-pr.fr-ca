---
title: "Reporter des paiements par prélèvement SEPA | Microsoft Docs"
description: "Lorsqu'un recouvrement prélèvement est correctement traité par votre banque, vous pouvez procéder au report de la réception du paiement pour les factures vente impliquées."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 2daa52e1ee4546356ecb7d94b5c01ab9e22bbbd6
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="post-sepa-direct-debit-payment-receipts"></a>Reporter des réceptions règlement de prélèvement SEPA
Lorsqu'un recouvrement prélèvement est correctement traité par votre banque, vous pouvez procéder au report de la réception du paiement pour les factures vente impliquées. Pour plus d'informations, voir [Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md).  

Vous pouvez valider la réception paiement directement à partir de la fenêtre **Recouvrements prélèvement** ou de la fenêtre **Écritures recouvrement prélèvement**. Vous pouvez également relayer le travail à un autre utilisateur en préparant les lignes journal associées.  

## <a name="to-post-a-direct-debit-payment-receipt-from-the-direct-debit-collections-window"></a>Pour reporter une réception de paiement de prélèvement à partir de la fenêtre Recouvrements de prélèvement  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Recouvrements prélèvement**, puis sélectionnez le lien associé.  
2. Sélectionnez une ligne pour une collection prélèvement automatique qui a été exportée vers un fichier bancaire et traitée avec succès par la banque. Pour plus d'informations, voir [Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md).  
3. Sélectionnez l'action **Reporter reçus paiement**.  
4. Dans la fenêtre **Valider recouvrement prélèvement**, renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**N° de recouvrement de prélèvement**|Spécifiez le recouvrement de prélèvement pour lequel vous souhaitez reporter la réception paiement.|  
    |**Modèle feuille comptabilité**|Spécifie le modèle de journal général à utiliser pour le report de la réception du paiement, comme le modèle pour les non réalisés.|  
    |**Nom feuille comptabilité**|Spécifie le lot journal général à utiliser pour le report de la réception du paiement.|  
    |**Créer feuille uniquement**|Activez cette case à cocher si vous ne souhaitez pas valider la réception règlement lorsque vous cliquez sur le bouton **OK**. La réception de paiements est préparée dans le journal spécifié et n'est pas reporté jusqu'à ce qu'une personne reporte les lignes journal en question.|  

5. Cliquez sur le bouton **OK**.  

## <a name="see-also"></a>Voir aussi  
 [Recouvrement de paiements par prélèvement automatique SEPA](finance-collect-payments-with-sepa-direct-debit.md)   
 [Ventes](sales-manage-sales.md)

