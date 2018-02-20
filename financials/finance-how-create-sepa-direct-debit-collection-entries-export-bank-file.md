---
title: "Exporter des écritures de collection prélèvement SEPA | Microsoft Docs"
description: "Créez une collection prélèvement, qui contient des informations sur le compte bancaire du client, les factures vente affectées et le mandat de prélèvement."
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 4a527467e40448d5ddd82a66b153c7cad761e7fb
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="create-sepa-direct-debit-collection-entries-and-export-to-a-bank-file"></a>Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire
Pour demander à la banque de transférer le montant du paiement du compte bancaire du client vers le compte de votre compagnie, vous créez un recouvrement de prélèvement, qui conserve des informations sur le compte bancaire du client, les factures de vente concernées et le mandat de prélèvement. À partir de l'écriture de collection prélèvement automatique qui en résulte, vous exportez ensuite un fichier XML que vous envoyez ou transférez à votre banque électronique pour traitement. La banque vous communiquera tous les paiements qu'elle n'a pas pu traiter, et vous devez rejeter manuellement les écritures de collection prélèvement automatique en question.  

> [!NOTE]  
>  Pour réunir les paiements à l'aide du prélèvement SEPA, la devise sur la facture vente doit être l'EURO.  

### <a name="to-create-a-direct-debit-collection"></a>Pour créer une collection prélèvement automatique  

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Recouvrements prélèvement**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Recouvrements prélèvement**, sous l'onglet **Accueil**, dans le groupe **Nouveau**, choisissez **Créer collection prélèvement automatique**.  
3. Dans la fenêtre **Créer recouvrement prélèvement**, renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Date d'échéance début**|Spécifiez la date d'échéance de paiement la plus proche sur les factures vente pour lesquelles vous souhaitez créer un recouvrement de prélèvement.|  
    |**Date d'échéance fin**|Spécifiez la date d'échéance de paiement la plus ancienne sur les factures vente pour lesquelles vous souhaitez créer un recouvrement de prélèvement.|  
    |**Type partenaire**|Spécifie si le recouvrement de prélèvement est réalisé pour des clients de type **Compagnie** ou **Personne**.|  
    |**Uniquement les clients avec mandat valide**|Spécifie si une collection de prélèvement est créée pour les clients disposant d'un mandat de prélèvement valable. **Remarque :** une recouvrement de prélèvement est créé même si le champ **Code mandat de prélèvement** n'est pas rempli sur la facture vente.|  
    |**Uniquement les factures avec mandat valide**|Spécifiez si un recouvrement de prélèvement est créé uniquement pour les factures vente si un mandat de prélèvement valide est sélectionné dans le champ **Code mandat de prélèvement** de la facture vente.|  
    |**N° compte bancaire**|Spécifie les comptes bancaires de votre compagnie sur lesquels le paiement collecté sera transféré à partir du compte bancaire du client.|  
    |**Nom compte bancaire**|Spécifie le nom du compte bancaire que vous sélectionnez dans le champ **N° compte bancaire**. Ce champ est complété automatiquement.|  

4. Cliquez sur le bouton **OK**.  

     Une collection prélèvement automatique est ajoutée à la fenêtre **Recouvrements prélèvement** et une ou plusieurs écritures de collection prélèvement automatique sont créées.  

### <a name="to-export-a-direct-debit-collection-entry-to-a-bank-file"></a>Pour exporter une collection prélèvement automatique vers un fichier bancaire  
1. Dans la fenêtre **Recouvrements prélèvement**, sous l'onglet **Accueil**, dans le groupe **Traitement**, choisissez **Écritures recouvrement prélèvement**.  
2. Dans la fenêtre **Écritures recouvrement prélèvement**, sélectionnez l'écriture que vous voulez exporter, puis sous l'onglet **Accueil**, dans le groupe **Traitement**, cliquez sur **Créer fichier prélèvement automatique**.  
3. Enregistrez le fichier d'exportation à l'emplacement où vous l'envoyez ou transférez\-le à votre banque électronique.  

     Dans la fenêtre **Écritures recouvrement prélèvement**, le champ **Statut recouvrement prélèvement** est modifié sur Fichier créé. Dans la fenêtre **Mandats de prélèvement SEPA**, le champ **Compteur prélèvements** est mis à jour avec un nombre.  

Si le fichier exporté ne peut pas être traité, par exemple parce que le client est insolvable, vous pouvez rejeter l'écriture de collection prélèvement automatique. Si le fichier exporté est correctement traité par la banque, les paiements dus des factures vente impliquées sont collectés automatiquement auprès des clients concernés. Dans ce cas, vous pouvez fermer la collection.  

### <a name="to-reject-a-direct-debit-collection-entry"></a>Pour rejeter une écriture collection prélèvement automatique  

* Dans la fenêtre **Écritures recouvrement prélèvement**, sélectionnez l'écriture qui n'a pas été traitée, puis sous l'onglet **Accueil**, dans le groupe **Traitement**, cliquez sur **Rejeter écriture**.  

     La valeur du champ **Statut** de la fenêtre **Écritures recouvrement prélèvement** est modifiée sur **Rejetée**.  

### <a name="to-close-a-direct-debit-collection"></a>Pour fermer une collection prélèvement automatique  
*  Dans la fenêtre **Écritures recouvrement prélèvement**, sélectionnez l'écriture qui a été traitée, puis sous l'onglet **Accueil**, dans le groupe **Traitement**, cliquez sur **Fermer collection**.  

     La collection prélèvement automatique associée est fermée.  

Vous pouvez maintenant passer au report des réceptions de paiement pour les factures vente impliquées. Vous pouvez généralement le faire pendant que vous validez des réceptions de paiement, tel que dans la fenêtre **Enregistrement de paiement**, ou vous pouvez valider les réceptions de paiement directement à partir de la fenêtre **Écritures recouvrement prélèvement**. Pour plus d'informations, voir [Reporter des réceptions règlement de prélèvement SEPA](finance-how-to-post-sepa-direct-debit-payment-receipts.md).  

## <a name="see-also"></a>Voir aussi  
[Configurer un prélèvement SEPA](finance-how-to-set-up-sepa-direct-debit.md)  
[Reporter des réceptions règlement de prélèvement SEPA](finance-how-to-post-sepa-direct-debit-payment-receipts.md)  
[Recouvrement de paiements par prélèvement automatique SEPA](finance-collect-payments-with-sepa-direct-debit.md)  

