---
title: Vendeurs de blocs
description: 'Découvrez comment empêcher l’inclusion de fournisseurs dans des transactions, ou simplement comment bloquer de nouveaux paiements qui leur sont destinés.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.search.form: 27
ms.date: 07/19/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="block-vendors"></a>Vendeurs de blocs
Vous pouvez bloquer un fournisseur, par exemple en raison d’une insolvabilité, afin que le fournisseur ne puisse pas être ajouté aux documents d’achat ou afin qu’aucun paiement ne puisse être enregistré pour le fournisseur.

Le tableau suivant décrit les options pour bloquer des fournisseurs.  

|Option|Description|  
|--------------------|------------|  
|**Vide**|Les transactions sont autorisées pour ce fournisseur.|
|**Règlement**|Aucun nouveau paiement ne peut être créé pour ce fournisseur.|  
|**Tout**|Aucune transaction n'est autorisée pour ce fournisseur.|  

## <a name="to-block-a-vendor"></a>Pour bloquer un fournisseur
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Fournisseurs**, puis choisissez le lien associé.
2. Sélectionnez le fournisseur que vous souhaitez bloquer.
3. Dans le champ **Bloqué**, choisissez l'une des options de blocage.

## <a name="see-also"></a>Voir aussi .
[Enregistrement des nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Effectuer des paiements](payables-make-payments.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
