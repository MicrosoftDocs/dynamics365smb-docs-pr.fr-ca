---
title: Créer un devis d’achat pour demander une offre
description: Décrit comment créer une offre vente ou une demande de devis pour enregistrer l'offre que vous avez faite à un client pour vendre des produits dans certaines conditions.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: rfq
ms.search.form: 49, 97, 9306, 9346
ms.date: 08/08/2022
ms.author: edupont
ms.openlocfilehash: 6444b795bf95b4da45d5d09bd6d6b7d5177c277a
ms.sourcegitcommit: 8b95e1700a9d1e5be16cbfe94fdf7b660f1cd5d7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2022
ms.locfileid: "9461140"
---
# <a name="request-quotes"></a>Demander des devis

Vous pouvez utiliser un devis en tant que phase préliminaire d’un bon de commande, et le convertir ensuite en facture achat.

## <a name="create-a-purchase-quote"></a>Créer un devis

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Devis**, puis sélectionnez le lien associé.
2. Créez un document, de la même manière que vous créez un bon de commande. En savoir plus sur [Enregistrer les achats](purchasing-how-record-purchases.md).

## <a name="convert-a-purchase-quote-to-a-purchase-order"></a>Convertir un devis en bon de commande

Lorsque vous avez accepté le devis du fournisseur, vous pouvez le convertir en bon de commande pour procéder à l’achat.

1. Ouvrez le devis à convertir, puis sélectionnez l’action **Créer commande**.

Le devis d'achat est supprimé de la base de données. Un bon de commande est créé sur la base des informations contenues dans le devis. Vous pouvez l'utiliser pour traiter l’achat et ensuite reporter une facture achat. Dans le champ **N° devis** de la facture achat ou du bon de commande, vous pouvez visualiser le numéro du devis à partir duquel il/elle a été réalisé(e).

> [!NOTE]
> Il n’est pas possible de convertir directement un devis d’achat en facture d’achat, comme c’est le cas avec les devis de vente. Pour plus de détails sur la création d’une facture d’achat, consultez [Enregistrer les achats avec les factures d’achat](purchasing-how-record-purchases.md).

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/create-purchase-documents-dynamics-365-business-central/).

## <a name="see-also"></a>Voir aussi .

[Procédure d'achat](purchasing-manage-purchasing.md)  
[Définition des achats](purchasing-setup-purchasing.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
