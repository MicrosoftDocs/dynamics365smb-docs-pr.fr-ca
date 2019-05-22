---
title: Créer un devis d'achat pour demander une offre | Microsoft Docs
description: Décrit comment créer une offre vente offrent ou un document de demande de proposition pour enregistrer votre offre à un client pour vendre des produits dans certaines conditions.
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: rfq
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: 109e00637b9e5a110005660bb108ec8e8a551345
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1252283"
---
# <a name="request-quotes"></a>Demander des devis
Vous pouvez utiliser un devis en tant que phase préliminaire d'un bon de commande, et convertir cette commande en facture achat ou en bon de commande.


## <a name="to-create-a-purchase-quote"></a>Pour créer un devis d'achat
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Devis**, puis sélectionnez le lien associé.
2. Créez un document, de la même manière que vous créez un bon de commande. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).

## <a name="to-convert-a-purchase-quote-to-a-purchase-order"></a>Pour convertir un devis en bon de commande
Lorsque vous avez accepté le devis du fournisseur, vous pouvez le convertir en facture achat ou en commande pour procéder à l'achat.

1. Ouvrez un devis d'achat qui est prêt à être converti, puis sélectionnez l'action **Créer commande**.

Le devis d'achat est supprimé de la base de données. Une facture achat ou un bon de commande basé sur les informations du devis et dans lequel vous pouvez traiter l'achat est créé. Dans le champ **N° devis** de la facture achat ou du bon de commande, vous pouvez visualiser le numéro de devis à partir duquel elle a été réalisée.

## <a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Définition des achats](purchasing-setup-purchasing.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
