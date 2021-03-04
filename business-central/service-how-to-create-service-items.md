---
title: 'Procédure : créer des articles de service | Microsoft Docs'
description: Lorsque vous recevez en maintenance un article non enregistré, vous pouvez l'enregistrer en tant qu'article de service.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: e45c23c8ed3b6f96c24e78666822c6fb9ef9859f
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4757902"
---
# <a name="create-service-items"></a>Créer des articles de service
Dans [!INCLUDE[prod_short](includes/prod_short.md)], le terme « article de service » fait référence à un équipement ou un article nécessitant une maintenance. Lorsque vous créez une commande service, vous spécifiez les articles nécessitant une maintenance. Dans la commande, vous pouvez lier un article de service à un article dans l'inventaire ou à un groupe articles de service.    

Lorsque vous recevez un article nécessitant une maintenance, vous pouvez l'enregistrer en tant qu'article de service. Plusieurs méthodes sont possibles. Par exemple, vous pouvez créer un article de service sur la page **Articles de service**, ou dans le cadre d'un autre traitement, par exemple en utilisant une commande service.   

## <a name="to-create-a-service-item"></a>Pour créer un article de service  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles de service**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-create-service-items-within-a-service-order"></a>Pour créer des articles de service dans des commandes service  
Lorsque vous recevez des articles que vous souhaitez enregistrer comme articles de service, vous pouvez les créer en tant que tels sur la page **Commande service** ou **Devis service**.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Commandes service**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choisissez l'action **Créer article de service**.  

    Un numéro est affecté à l'article de service et une fiche article de service est créée. Le champ **N° article de service** est rempli par le numéro du nouvel article de service.

## <a name="to-create-a-service-item-when-shipping-items"></a>Pour créer un article de service lors de la livraison d'articles  
Si vous livrez des articles en reportant les documents de vente ou les factures vente, ces articles sont enregistrés automatiquement en tant qu'articles de service si la condition suivante est remplie. Les articles doivent appartenir à un groupe articles de service et la case à cocher **Créer article de service** doit être activée. Si ces articles portent des numéros de série enregistrés sur la page Lignes traçabilité, cette information est copiée automatiquement dans le champ **Numéro de série** de la fiche article de service, lorsque les articles de service sont créés.  

La procédure suivante explique comment créer des articles de service lorsque vous livrez des articles de documents de vente.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Ouvrez le document de vente approprié.  
3. Sélectionnez l'action **Reporter** ou **Reporter et imprimer**.  
4. Choisissez l'action **Livrer** ou **Livrer et facturer**.  
5. Les articles de service sont automatiquement créés pour les articles de la commande pour autant qu'ils appartiennent à un groupe articles de service que vous avez configuré pour créer des articles de service. Si vous avez enregistré des numéros de série précis sur la page **Lignes traçabilité**, ceux-ci sont affectés à ces articles de service.  

> [!NOTE]  
>  Si un article est une nomenclature et que vous ayez éclaté cette nomenclature, les articles de la nomenclature éclatée sont traités comme des articles normaux. Des articles de service sont créés à partir des mêmes conditions (groupe articles de service et numéro de série). En outre, si le programme crée un article de service pour un article nomenclature éclatée composé d'autres composantes nomenclature, ces articles sont créés comme composantes d'article de service de l'article de service de la nomenclature éclatée.  
>   
>  Si un article est une nomenclature que vous n'avez pas éclatée, un article de service est créé à partir des mêmes conditions (groupe articles de service et numéro de série).  

## <a name="to-insert-a-starting-fee-for-a-service-item"></a>Pour insérer des frais forfaitaires pour un article service
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Tâches service**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Feuille activité article**.
3. Choisissez la ligne service, puis sélectionnez **Actions**, **Fonctions**, puis l'action **Insérer frais forfaitaires**.  

    Une ligne service de type **Coût** est insérée avec les frais forfaitaires. Les frais forfaitaires affectent l'article de service sélectionné.

## <a name="see-also"></a>Voir aussi  
[Configurer les articles de service et les composantes article de service](service-how-setup-service-items.md)  
[Paramétrage de la gestion des services](service-setup-service.md)  
[Gestion des services](service-service.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]