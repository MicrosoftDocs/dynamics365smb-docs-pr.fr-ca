---
title: Procédure de configuration des méthodes d'expédition | Microsoft Docs
description: Vous pouvez définir un code pour chacune de vos méthodes de livraison offertes, par exemple, saisir les informations qui les concernent.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: incoterms
ms.date: 06/17/2019
ms.author: sgroespe
ms.openlocfilehash: 7248f49e92db98cec047d2035ce82d7caf84799f
ms.sourcegitcommit: 6dc83b27ac47f3b39a7b84cfb7446e7f48b8ce63
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/17/2019
ms.locfileid: "1632793"
---
# <a name="set-up-shipment-methods"></a>Configurer les méthodes de livraison
Les méthodes de livraison, également appelées incoterms, dépendent souvent des articles, des clients et des fournisseurs. Par exemple, si le client habite sur une île, il peut choisir d'être toujours livré par voie aérienne ou maritime. Certains clients peuvent exiger une livraison le lendemain. Certains voudront peut-être récupérer la commande. Vous pouvez spécifier le type de livraison souhaité sur les fiches client et les fiches fournisseur.

Vous définissez la description et le code de chaque méthode de livraison sur la page **Méthodes de livraison**. Par exemple, vous définissez le code F.O.B., et saisissez Franco bord dans le champ **Description**. Vous pouvez ensuite saisir ce code dans les champs **Code de méthode de livraison** ailleurs dans le système, par exemple sur une fiche client. Ensuite, lorsque vous créez des commandes, des factures, des notes de crédit, etc., le système copie la description représentée par le code. Au besoin, vous pouvez le modifier sur le document.

## <a name="to-set-up-a-shipment-code"></a>Pour configurer un code de livraison
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Méthodes de livraison**, puis sélectionnez le lien associé.
2. Sur la page **Méthodes de livraison**, sélectionnez l'action **Nouveau**.
3. Sur la nouvelle ligne, indiquez un code et une description pour les méthode de livraison.

## <a name="see-also"></a>Voir aussi
[Incoterms](https://iccwbo.org/resources-for-business/incoterms-rules)  
[Configurer des agents de livraison](sales-how-to-set-up-shipping-agents.md)  
[Suivre des colis](sales-how-track-packages.md)    
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
