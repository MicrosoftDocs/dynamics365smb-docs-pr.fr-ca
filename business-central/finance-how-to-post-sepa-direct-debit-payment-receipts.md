---
title: Reporter des paiements par prélèvement SEPA | Microsoft Docs
description: Lorsqu'un recouvrement prélèvement est correctement traité par votre banque, vous pouvez procéder au report de la réception du paiement pour les factures vente impliquées.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
redirect_url: finance-collect-payments-with-sepa-direct-debit
ms.openlocfilehash: 6c646575ba803358aa00309ce02742423bcc7de8
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1242662"
---
# <a name="post-sepa-direct-debit-payment-receipts"></a>Reporter des réceptions règlement de prélèvement SEPA
Lorsqu'un recouvrement prélèvement est correctement traité par votre banque, vous pouvez procéder au report de la réception du paiement pour les factures vente impliquées. Pour plus d'informations, voir [Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md).  

Vous pouvez reporter la réception paiement directement à partir de la page **Recouvrements prélèvement** ou de la page **Écritures recouvrement prélèvement**. Vous pouvez également relayer le travail à un autre utilisateur en préparant les lignes journal associées.  

## <a name="to-post-a-direct-debit-payment-receipt-from-the-direct-debit-collections-page"></a>Pour reporter une réception de paiement de prélèvement à partir de la page Recouvrement prélèvement  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Recouvrements prélèvement**, puis sélectionnez le lien associé.  
2. Sélectionnez une ligne pour une collection prélèvement automatique qui a été exportée vers un fichier bancaire et traitée avec succès par la banque. Pour plus d'informations, voir [Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md).  
3. Sélectionnez l'action **Reporter reçus paiement**.  
4. Sur la page **Reporter recouvrement prélèvement**, renseignez les champs comme indiqué dans le tableau suivant.  

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
