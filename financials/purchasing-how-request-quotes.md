---
title: "Créer un devis d'achat pour demander une offre à votre fournisseur | Microsoft Docs"
description: "Décrit comment créer une offre vente offrent ou un document de demande de proposition pour enregistrer votre offre à un client pour vendre des produits dans certaines conditions."
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: rfq
ms.date: 08/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: aa56764b5f3210229ad21eae6891fb201462209c
ms.openlocfilehash: df1793d811dea11c01ff5e7d90a9f52b9e987c13
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---
# <a name="how-to-request-quotes"></a>Procédure : Demander des devis
Vous pouvez utiliser un devis en tant que phase préliminaire d'un bon de commande, et convertir cette commande en facture achat ou en bon de commande.


## <a name="to-create-a-purchase-quote"></a>Pour créer un devis d'achat
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Devis d'achat**, puis sélectionnez le lien associé.
2. Créez un document, de la même manière que vous créez un bon de commande. Pour plus d'informations, reportez-vous à [Procédure : enregistrer des achats](purchasing-how-record-purchases.md).

## <a name="to-convert-a-purchase-quote-to-a-purchase-order"></a>Pour convertir un devis en bon de commande
Lorsque vous avez accepté le devis du fournisseur, vous pouvez le convertir en facture achat ou en commande pour procéder à l'achat.

1. Ouvrez un devis d'achat qui est prêt à être converti, puis sélectionnez l'action **Créer commande**.

Le devis d'achat est supprimé de la base de données. Une facture achat ou un bon de commande basé sur les informations du devis et dans lequel vous pouvez traiter l'achat est créé. Dans le champ **N° devis** de la facture achat ou du bon de commande, vous pouvez visualiser le numéro de devis à partir duquel elle a été réalisée.

## <a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Définition des achats](purchasing-setup-purchasing.md)  
[Procédure : envoyer des documents par e-mail](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

