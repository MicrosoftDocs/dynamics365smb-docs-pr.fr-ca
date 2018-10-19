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
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: ee07ca7ba498858fac794f1ee1f27f281de8ae02
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="post-sepa-direct-debit-payment-receipts"></a>Reporter des réceptions règlement de prélèvement SEPA
Lorsqu'un recouvrement prélèvement est correctement traité par votre banque, vous pouvez procéder au report de la réception du paiement pour les factures vente impliquées. Pour plus d'informations, voir [Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md).  

Vous pouvez valider la réception paiement directement à partir de la fenêtre **Recouvrements prélèvement** ou de la fenêtre **Écritures recouvrement prélèvement**. Vous pouvez également relayer le travail à un autre utilisateur en préparant les lignes journal associées.  

## <a name="to-post-a-direct-debit-payment-receipt-from-the-direct-debit-collections-window"></a>Pour reporter une réception de paiement de prélèvement à partir de la fenêtre Recouvrements de prélèvement  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Recouvrements prélèvement**, puis sélectionnez le lien associé.  
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

