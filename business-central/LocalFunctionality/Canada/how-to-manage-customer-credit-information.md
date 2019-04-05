---
title: 'Procédure : gérer les renseignements sur le crédit client | Microsoft Docs'
description: Dans Business Central, vous pouvez ajouter des commentaires aux renseignements sur le crédit client. Vous pouvez aussi mettre en attente et bloquer des clients présentant une mauvaise situation de crédit avant la livraison ou la facturation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2018
ms.author: sgroespe
redirect_url: ../../receivables-how-block-customers
ms.openlocfilehash: 15f58025a038c0b8868fbceef51c5a74e0bbb61d
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "826565"
---
# <a name="manage-customer-credit-information"></a>Gérer les renseignements sur le crédit client
Dans [!INCLUDE[d365fin](../../includes/d365fin_md.md)], vous pouvez ajouter des commentaires aux renseignements sur le crédit client. Vous pouvez aussi mettre en attente et bloquer des clients présentant une mauvaise situation de crédit avant la livraison ou la facturation.  

## <a name="to-add-comments-to-customer-credit-information"></a>Pour ajouter des commentaires aux renseignements sur le crédit client  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Gestion de crédit**, puis sélectionnez le lien associé.  
2.  Sur la page **Liste des clients - Gestion de crédit**, sélectionnez un client, puis choisissez l'action **Commentaires**.  
3.  Sur la page **Feuille de commentaires**, renseignez les champs comme indiqué dans le tableau suivant.  

    |Champ|Description|  
    |---------------------------------|---------------------------------------|  
    |**Date**|Date du commentaire.|  
    |**Commentaire**|Commentaire sur le client. Vous pouvez entrer 80 caractères alphanumériques maximum.|  

4.  Cliquez sur le bouton **OK**.  

## <a name="to-prevent-an-order-from-shipping-or-invoicing"></a>Pour éviter la livraison ou la facturation d'une commande  
1.  Sélectionnez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.  
2.  Sélectionnez le client, puis choisissez l'action **Écritures**.  
3.  Dans le champ **En attente**, entrez les initiales du client.  
4.  Cliquez sur le bouton **OK**.  

    > [!NOTE]  
    >  Vous devez disposer d'une autorisation de sécurité adéquate pour ajouter ou supprimer des mises en attente de documents de vente spécifiques à l'aide du champ **En attente**.  

## <a name="to-block-a-sales-order-for-a-customer"></a>Pour bloquer un document de vente pour un client  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Clients**, puis sélectionnez le lien associé.  
2.  Sélectionnez un client, puis cliquez sur l'action **Modifier**.  
3.  Sur le raccourci **Général**, dans le champ **Bloqué**, sélectionnez une des options suivantes :  

    -   **<Blank>** – La transaction est autorisée pour ce client.  
    -   **Livrer** – Il n'est pas possible de créer de nouvelles commandes ni de nouvelles livraisons pour ce client. Les livraisons existantes qui ne sont pas encore facturées peuvent être facturées.  
    -   **Facturer** – Il n'est pas possible de créer de nouvelles commandes, de nouvelles livraisons ni de nouvelles factures pour ce client. Les livraisons existantes qui ne sont pas encore facturées ne peuvent pas être facturées.  
    -   **Tout** – Aucune transaction n'est autorisée pour ce client, y compris les paiements.  
4.  Cliquez sur le bouton **OK**.  

## <a name="see-also"></a>Voir aussi  
[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance.md)
